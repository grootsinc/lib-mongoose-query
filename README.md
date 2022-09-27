# Mongoose Query Parser

```js
const mongooseQueryParser = require("mongooseQueryParser");

getUsers = async (req) => {
	// Parse your API query
	let query = await mongooseQueryParser.parse(req);

	// Pass to Sequelize model find...() functions
	return User.find(query);
};
```

## Features and Syntax with examples

-   Querying with sequelize JSON format

```js
// Find where firstname is Sourab and id is 1 or firstName is Almas and id is 2
?query={"or": [{"and": [{"firstName": "Sourab"}, {"id": 1}]}, {"and": [{"firstName": "Almas"}, {"id": 2}]}]}
```

## Operators

Just use sequelize format query in the API requests  
substituting Sequelize operators with below keys.

```
	gt: "$gt",
	gte: "$gte",
	lt: "$lt",
	lte: "$lte",
	ne: "$ne",
	eq: "$eq",
	not: "$not",
	regexp: "$regex", // REGEXP/~ '^[h|a|t]' (MySQL/PG only)
	notRegexp: "Op.notRegexp", // NOT REGEXP/!~ '^[h|a|t]' (MySQL/PG only)
	and: "$and", // AND (a = 5)
	or: "$or", // (a = 5 OR a = 6)
	nor: "$nor", // !(a = 5 OR a = 6)
	between: "Op.between", // BETWEEN 6 AND 10
	notBetween: "Op.notBetween", // NOT BETWEEN 11 AND 15
	in: "$in", // IN [1, 2]
	notIn: "$nin", // NOT IN [1, 2]
```

## Installation

```
npm install -s https://github.com/grootsinc/lib-mongoose-query.git
```

## Contributing

I really appreciate your help in any case.  
Fixes, Improvements, Enhancements, Documentation.

To contribute, please create a pull request to `main` branch.
