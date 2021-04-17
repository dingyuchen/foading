# SherLock: Unsupervised Synchronization-Operation Inference

## Problem Formulation

Synchronization helps to enforce a happens-before relationship.

Many tools that analyze concurrent programs rely on understanding the semantics of program synchronization and the happen-before relationship induced by them.
Typically, these tools rely on manual specification.

Low-level primitives like atomic operations do not always enforce a happen-before relationship.
Threading and locking APIs are complex and semantic-rich, making it difficult to annotate.

Synchronization inference is a _dynamic unsupervised_ probabilistic inference problem.
SherLock is a tool for identifying program synchronizations.

### High Level Idea

At a high level, SherLock is based on the idea that all synchronizations are used to order events that would otherwise result in bugs.

> What if result of program execution is independent on synchronization?

SherLock identifies synchronizations by relying on the following insights:

1. Most (if not all) such conflicting accesses in mature programs are properly synchronized.
2. Design a set of properties and hypotheses that reflect assumptions of synchronizations and their behavior. Pinpoint synchronizations through multiple executions.
3. Perturb the execution at strategic locations to improve inference.

### Components of SherLock

1. Observer
   1. This component instruments software binaries and produces execution traces under the provided inputs.
2. Solver
   1. Processes all the observations collected
   2. Identifies a set of acquire and release synchronizations
   3. Linear Solver
3. Perturber
   1. Inject delays at strategic points of execution

# What Are Synchronization Behaviors

Identifying synchronizations without understanding the semantics of underlying framework, library, or operating system that implements them.

## Definition

Any instruction or operation in the application that enforces a happen-before relation across threads.

In this paper, we consider every synchronization, acquire or release, to take one of these forms:

1. read of a heap variable
2. write to a heap variable
3. an invocation or entry point of an API or method
4. exit of an API or method

## Properties

Hard constraints

### Read-Acquire and Write-Release

1. heap read does not change system states and hence cannot be a release synchronization
2. heap write cannot perceive what is going on in the system, hence cannot be an acquire synchronization
3. method's exit as a release;
4. method's invocation as an acquire - never the other way round

## Hypotheses

### Mostly Protected

Most, if not all, conflicting accesses in a mature software should be synchronized.

### Synchronizations are Rare

Synchronizations should constitute a small portion of all operations.

It is unlikely for the same synchronization to occur many times.

### Acquisition-Time Mostly Varies

How long a thread needs to wait during an acquire varies a lot at runtime.

If every execution of a method $m$ takes roughly the same amount of time, the invocation of $m$ is unlikely to be an acquire.

### Mostly Paired

Given the strong semantic connection between a release and its corresponding acquire, they are often defined in a paired or clustered way in well-maintained software.

Specifically, if the read of a variable `C::v` is used for acquire synchronization, the corresponding release synchronization is very likely the write of the same variable `C::v`.

## Interesting Behaviors

In every run, SherLock injects delays around those top synchronization candidates based on previous runs so that the software's reaction towards these delays can either strongly support or dispute existing inference results.

True synchronizations to surface after 1-3 runs.

# SherLock Implementation

## Observer

SherLock instruments a given application to trace 2 types of operations during run time.

1. Read/write operations that may form conflicting-access pairs useful for Mostly-Paired Hypothesis.
   1. read from or write to heap variables (public fields of a class)
   2. getter and setter methods of public properties of a class
   3. invocations of read/write APIs of thread-unsafe libraries (`List.add()`)
2. Accesses to heap variables and entry and exit of methods

### Log Entry Content

1. timestamp
2. threadID
3. operation type 
   1. read
   2. write
   3. method entry
   4. method exit
4. field name and its memory address for each read/write operation
5. method name and parent object id for each method entry/exit operation

### Forming acquire/release windows

SherLock uses a physical time window `Near` to filter out less useful pairs.

Set a limit to the maximum time between 2 conflicting accesses.

SherLock sets an upper bound (15) for the number of windows that one location pair can form.

## Solver

### Overall objective function

$$\sum_w (rel(w) + acq(w)) + \lambda \bigg [\sum_c pair_c(c) + \sum_f pair_f(f) + \sum_v reg(v) + \sum_v rare(v) + \sum_m var(m) \bigg]$$

At least one variable in the acquire/release window to be an acquire/release, number of synchronizations should also be minimized.
This together prevents trivial solutions.

## Perturber and Feedback

1. Adding new variables and corresponding constraints if new synchronization candidates show up
2. Adding new objective function terms for every newly observed release window
3. Updating existing objective function terms, eg. average occurrence of a candidate operation, the co-efficient of variance of a method's duration, etc.

> How are new candidates detected?

### Data race

This occurs when SherLock observes a concurrent execution of two conflicting accesses with every operation in the acquire (release) window guaranteed to not be an acquire (release) synchronization.
This can happen when either the acquire (release) window is empty or every operation in the window is a write (read) operation.

SherLock remembers and removes all the `Mostly Protected` penalty term associated with the acquire and release windows between $a$ and $b$ in all runs.

After every run, the Perturber injects a 100ms delay right before every dynamic instance of every operation that is currently considered as a release synchronization by the solver.

# Results

SherLock successfully identifies many real synchronizations.
Of the 133 synchronizations identified, 122 are unique across the applications.

Outperforms FastTrack

## Missed Synchronizations

For example `UpgradeToWriteLock` releases a reader lock and then acquires a writer lock all inside one API.
This resulted in 1 missed synchronization and 15 false data-race reports.

Future SherLock can try turning the Single-Role assumption into a soft constraint.

Inability to refine the windows effectively.
These include failures to identify the acquire pair for object disposals, the release pair for static constructors, and other synchronization.
For instance, dispose functions are often called during garbage collection which can execute at a much later time after the pairing release instruction that removes the last reference to the object.

