# 1.1 Introducing MongoDB
* open source noSQL - not relational, no query language
* good for unstructured data
* mongo uses collections, which are made of documents.
* documents are independent, can store documents with different fields together
* ex. potions have different data, this is called dynamic schema
* documents are just like JSON objects

# 1.5 Queries and Data Types
* mongo will do a unique id for each document, by default
* objects are like JSON, persisted in a format called BSON
* you can store strings, numbers, bools, arrays, objects, and null
* also have object id and date
* mongo persists floats precisions
* use dot notation to query.

# 2.1 Removing and Modifying Documents
* remove collection method will delete documents that match the query
* can also update fields in documents
* so for update method, then do the update operator ex.
	* {"name": "love", "$set": {"price": 2.99}}
* can take third parameter for options ex. multi
* you can record views, use update and $inc
* if you do upsert as an option, it will create the document if it doesn't exist

# 2.7 Advanced Modifications
* use $unset to remove an operator
* empty brackets passed in first {}, selects all documents
* update a field name with $rename
* can use dot notation to access arrays.
* positional operator placeholder which will set proper position for value, this lets 
* $max, lets you update only if new val is greater than curr val
* $min, and $mul (multiplies)
* $pop will remove first or last val in an array.
* $push to add to end of array

# 3.1 Query Operators
* can pass multiple queries, by passing in comma-separated queries
* comparison query operators match docs based on comparisons

# 3.8 Customizing Queries
* projections allow you to specify what fields you want so you can create custom results
* if you want to exclude a few fields set them to false, you'll get the rest
* if you want specific fields set those to true, rest will be false except id
* can only mix true false with _id in there.

# 4.1 Data Modeling
* cautious to keep duplicated data, because it's hard to keep consistent throughout the database
* instead of embedding vendor info, can create a vendors collection and reference vendor document in each potion document.
* embedding:
	* only need one query
	* atomic write operations
* mongo doesn't recognize document relationships, so there aren't transactions

# 4.8 Data Modeling Decisions
* two options, embedding vs referencing
* data thats frequently used together will benefit from being embedded
* the larger the data size, the better referencing is ex. 100+ is when you should consider referencing
* will data change often? if so you should reference, otherwise embed.
* potion -> comments barely change so embedding
* user info -> reference because it'll change often or it can
* generally embedding is the best starting point
* consider referencing with large data sizes

# 5.1 Common Aggregations
* mongo comes with an aggregation framework which manipulates data before you get it
* accumulator takes a single expression and computes the expression for grouped documents
* when fields begin with a $ they are operators that a performing a task, if a value starts with a dollar sign it's pointing to the value
* shits dope.

# 5.7 The Aggregation Pipeline
* aggregate method acts like pipeline, can pass data through many stages to change it along the way
* $match is a query and will only pass documents if they meet specific conditions
* $project allows you to send only the fields you want, so when you group by grade say, you don't need id