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
* 