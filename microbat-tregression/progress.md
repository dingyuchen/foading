# Progress

## Build Tool

- Program requires the use of `sav.commons` project, which is not a maven project
  - converted to a maven project
- The conversion of `sav.commons` into a maven project causes many problems since many of the dependencies are not included in the maven file
- Using maven to generate `.classpath` and `.project` files result in build errors
  - Unable to revert
  - have to restart
- Both build tools require explicitly adding `org.eclipse.jdt/platform` as dependencies
  - both build tools are unable to resolve for `JDIPlugin` in `BootstrapPlugin`
- using gradle as build tool instead
  - importing `org.eclipse`
  - https://stackoverflow.com/questions/62057321/using-swt-in-gradle-could-not-resolve-all-dependencies
  - Not being able to detect test classes in `/src/main`
    - It seems like it is impossible to incrementally adopt maven OR gradle as a build tool. It has to be done in 1 go.

## Testcases

- Static methods
  - Trivially testable
- non-static methods
  - internal state (`MethodCallStack`, `TrackingDelegate`) are not exposed for testing
- Integration testing
  - Instrumentator does not have a pure output
    - need to initialize an in-memory sqlite instance.
    - compare all db entries
    - [ ] require random UUID generation to be dependency injected
  - Require an sample test program
    - Test must spin up a JVM and instrument the program with a compiled instrumentator
      - How to do this?
        - refer to start debug handler

## GraphQL

- ApolloServer main use-case is for federating disjoint databases.
  - Can consider if in the future, there are information split across sql and nosql databases
  - For microbat, it is unnecessary to create a node server just to interface with the databases.
    - we will add the neo4j client and query the trace information with `Cypher` directly.
- Graph querying is dependent on the `ExecutionTracer` update that allows for pipelined storage queries
  - `ExecutionTracer` pipeline storage is blocked due to issues with build tool for refactoring
  - will go ahead with refactoring and add graph db in a separate branch
    - refactoring will be done asynchronously (meetings needed)
