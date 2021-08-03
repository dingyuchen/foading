# Less Quanta - Motion 

## Overview

`Motion` is an extensible rule evaluator built for lawyers by lawyers (mostly).

It solves 2 problems:

1. Allow the layman to check if they are adhering to complicated regulations, without requiring a full understanding of the regulation and all its edge cases
2. Allow lawyers to express arbitrary regulations as a logical statement that can be evaluated by computers, without coding

Essentially, `Motion` is an extension and improvement over [Notion](https://www.notion.so/)'s `Filter Group` features, with added support for `struct` definition.

## User Stories

> As a [target demographic], I would like to [feature request] (so that [rationale] _optional_)

### Users

- As a non-law-savvy person, I would like to input my current situation and get instant feedback on whether I am complying with the latest regulations, so that I do not bear the cognitive load of searching and understanding the latest regulations.
- As a non-law-savvy person, I would like to know which clause/part of the regulation I am not compliant with, so that I may rectify it accurately, without having to enumerate through all the rules.

### Lawyers

- As a lawyer, I would like to point non-law-savvy people to a foolproof and accurate resource to answer their personalized questions, so that I do not have to answer repeated questions.
- As a lawyer, I would like to be able to change and update the regulation expression as it is revised, without having to regenerate new forms or approaching a developer to explain the new regulations.
- As a lawyer, I would like to be able to update or create regulation expressions easily, so that the work is not tedious
- As a lawyer, I would like to be able to test and debug if my expression is correct, so that the evaluator does not provide bad legal advice.

## Technical Specifications

### Feature List

| Feature              | Priority | Difficulty | Notes                                                               |
| -------------------- | -------- | ---------- | ------------------------------------------------------------------- |
| Evaluation Engine    | High     | Medium     | Must do                                                             |
| Expression CRUD      | High     | Medium     | Follow backend api                                                  |
| Input UI             | High     | Medium     | UI Focused                                                          |
| Expression Database  | Medium   | Low        | Good to have                                                        |
| Expression Tester    | Low      | Low        | Nice to have                                                        |
| Authentication Logic | Low      | High       | Nice to have (Set all recorded regulations as public for hackathon) |

### Definitions

- Constant : fixed argument (eg, `2` in `x < 2`)
- Variable : an unknown argument (eg, `x` in `x < 2`)
- Expression : 
  - a constant or variable
  - a logical conjunction or disjunction of 2 expressions
  - a negation of an expression
  - a group
- Group : a collection of 1 or more expressions in conjunction or disjunction (Acts as parenthesis)
- Rule : 1 or more groups with a name/description (Acts as label)
- Attributes : one of the following types:
  - Date
  - Number
  - Enum / Tag / Status
  - Boolean
  - Collection of Attributes
  - Optional of Attribute
  - Self-defined Model
    - Note model must be optional to prevent non-terminating program
- Model : An object with an arbitrary number of attributes

### Functions

- Date
  - isBefore
  - isAfter
  - isBetween
- Number
  - `>`
  - `<`
  - `<=`
  - `>=`
  - `=`
- Enum
  - is
  - isNot
- Boolean
  - isTrue
  - isFalse
- Collection
  - allOf
  - noneOf
  - anyOf / oneOf
  - numberOf
- Optional
  - exists
  - existsAnd
- Model
  - attribute access

## Implementation Details

### Tech Stack

- Frontend
  - ReactJs
- Backend
  - Go
  - Postgresql
- DevOps
  - Docker Compose
  - Heroku

#### Responsibilities

| Frontend                    | Backend                                         |
| --------------------------- | ----------------------------------------------- |
| Create new models and rules | Persists models and rules into database storage |
| Obtain user input           | Delete rules and corresponding `regulations`    |
| Evaluate user input         |                                                 |

### Database Schema

#### Rules Table

```sql
CREATE TABLE rule (
	rule_id INT AUTO_INCREMENT PRIMARY KEY,
	rule_name VARCHAR(63) NOT NULL,
	rule_expr VARCHAR(511) NOT NULL
)
```

#### Regulations Table

```sql
CREATE TABLE regulation (
	rule_id INT NOT NULL,
	model_id INT NOT NULL,
	PRIMARY KEY (rule_id, model_id),
	FOREIGN KEY (rule_id) REFERENCES rule (rule_id) ON DELETE CASCADE,
	FOREIGN KEY (model_id) REFERENCES model (model_id)
)
```

> Create index on `rule_id`

#### Model Table

```sql
CREATE TABLE model (
	model_id INT PRIMARY KEY,
	model_expr VARCHAR(511) NOT NULL
)
```
### Json Schema

#### Model Definition

used to generate input suggestions

```js
{
	name : modelName,
	type : modelName, // a model is its own type
	attributes: [
		{
			name : attributeName,
			type : attributeType,
			value? : subType, // for collections
		}, ...
	]
}
```

#### Model Instance Schema

input for evaluation

```js
{
	value : [
		{
			attributeName : {
				value : value,
			}, ...
		}, ...
	]
}
```

#### Rule Definition

```js
{
	input : inputType
	name : label
	expr : {
		type : opName,
		arguments : [
			...
		]
	}
}
```

### Request Schema

Goal is to support `CREATE`, `READ` and `DELETE` for demo.

#### Create new rule

```js
POST@ "/regulation"
Content Body:
{
	models: [...], // static analysis can be applied to remove unused models
	rule: {
		input : inputType
		name : label
		expr : {...}
	}
}

Response:
Status 200 OK
```

#### Get all rules
```js
GET@ "/regulation"

Response Body:
[{
	models: [
		{
			model_id: model_id,
			name : modelName,
			type : modelName,
			attributes: [...],
		}, ...
	],

	rule_id: rule_id,
	rule: {
		input : inputType
		name : label
		expr : {...}
	}
}, ...]
```

#### Delete rule

```js
DELETE@ "/rule/:id"

Response:
Status 200 OK
```