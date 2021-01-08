Welcome to MongoDB introducing presentation. Today i will give you a basic information of MongoDB database, its definitions, short history, architecture and features. Lets start from brief MongoBD story.

The history of MongoDB started in 2007 from a company called 10gen. 10gen began developing MongoDB as a part of a planned platform as a service product.
Development on the new database was carried out from 2007 to 2009. The core engine was written in C++. The database was named MongoDB, since the idea was to store and process humongous amount of data.
The developer team decided to focus just on the MongoDB database, instead of the initial service product. The business idea was to release the database as an open source free download, and offer commercial support and training services.
MongoDB version 1 was released in February 2009.

At this slide you can see the major milestones of MongoDB evolution.
In 2013 10gen realised the true business potential and was renamed as MongoDB Inc. to focus on the database product.
One of the big problems at the beginning of MongoDB was its quite weak storage engine, used for saving and managing the data on a disk. The company's first acquisition was WiredTiger project, which created a stable storage engine with the same name.

Next major release of MongoDB was version 3 at March 2015 with the new WiredTiger storage engine.
In 2018 the MongoDB bought mLab company. This company was providing MongoDB as a service on the cloud, and had a large number of customers. With this aquisition MongoDB Inc. could developed its own Atlas cloud platform.

MongoDB is a document-based NoSQL database. It can run on Windows, Linux and Macintosh operational systems. The open source version is available as a free download.
MongoDB stores data entities in a container, which called collection, and each piece of data is stored in a JSON document format.
MongoDB has its own a console client called MongoDB shell. This is a JavaScript environment allows you to add, remove, edit or query document data.

NoSQL abbreviation means "non-SQL" or "non-relational". A NoSQL database provides a mechanism for data storage and retrieval, other than used in relational databases.
The data structures used by NoSQL databases are key–value pair, wide column, graph and document. They are different from used in relational databases, making some operations faster in NoSQL case.

A document-oriented database is a specialized key-value store and belongs to NoSQL category.
A key difference between the document-oriented and relational models, is that the data formats are not predefined in the document case.
Relational databases generally store data in separate tables, that are defined by the programmer, and a single object may be spread across several tables.
Document databases store all information for a given object in a single instance in the database, and every stored object can be different from every other.

BSON abbreviationif a short for binary JSON, a binary form of JSON-like documents.
I will introduce this later in features chapter.

The MongoDB architecture diagram shows the major components in the MongoDB server, sa following.

MongoDB supports drivers for 13 languages including Java, Node.JS, Python, PHP and Swift.
MongoDB ships with three supported storage engines, all of which can coexist within a single MongoDB replica set:

The default WiredTiger storage engine
The Encrypted storage engine that protecting data. (Requires Enterprise version)
The In-Memory storage engine, delivering the increased performance and real time analytics for the most demanding applications, that sensitive to low latency. (This is also requires enterprise version)
The MMAP version 1 engine, that was used only before 4.2 release.


Now lets talk about MongoDB features.

Aggregation: This operations process data records and return the computed results. It is similar to the GROUPBY operation in SQL. Examples are sum, avg, min, max, etc.
Document-oriented: The document structure is more similar with that, how developers describe objects in programming languages. That means objects are not in rows and columns, but have a structure as key-value pairs.
Schema-less database: In MongoDB the documents don’t need to have a predefined schema. The MongoDB data modelling allows you to represent hierarchical relationships, to store arrays and other complex structures.
Grid File System: For storing and retrieving large files GridFS is used in Mongo. GridFS is a file system that only stores the files, and their data is stored within MongoDB collections. GridFS can store files, greater than its document size, within the limit of 16 MB.


Another important feature is MapReduce.
The "map" operation can write results to a collection. If you perform the subsequent "reduce" operation on the same input collection, then it merges, or replaces, or reduces the new results with the previous results.
MapReduce can also be used for aggregation operations.


MongoDB uses BSON data format while storing documents in collections.
As a primary key, the BSON uses "underscore id" field by default. This field should have a unique value, which is called ObjectId, that generated either manually or automatically.
In some cases BSON uses more space than JSON. The reason for this is traversability goal of BSON. It is adds "extra" information to documents, like length of strings and sub-objects. This makes traversal faster.
BSON is also designed to be fast to encode and decode. For example, integers are stored in integer format, so they don't need to be parsed to and from text. This uses more space than JSON for small values, but is much faster to parse.
Also BSON supports additional data types, like BinData and Date.

MongoDB provides sharding to overcome scaling problem of web or mobile application. Sharding is a method, in which data is distributed across multiple machines. Sharding provides horizontal scalability.
Each shard holds some part of the data as a separate database. Merging all the shards together forms a single logical database. Operations over here are performed by query routers.

MongoDB supports range query, regular expression and other types of searches. The queries include user-defined JavaScript functions, and they return specific fields of a document.
This is an example of the difference between a SQL query and a MongoDB query.

MongoDB index is used to improve the performance of searches. Any field in a MongoDB document can be indexed as either primary or secondary. This lets the database engine efficiently resolve queries.

On the other hand, there are still areas where MongoDB doesn’t perform well. Here are some of the downsides of MongoDB:
Joins
Joining documents in MongoDB is no easy task. Pulling data from several collections requires a number of queries, which will lead to messy code and long latency. This feature is in development now.
Indexing
Quick speeds and high performance is only possible with the right indexes. With badly implemented and out of order composite indexes, MongoDB will operate at a very slow speed.
Duplicates
The relationships in MongoDB are not typically well-defined, and this could lead to duplicate data.

It is good to implement MongoDB for the collections of data that have not tightly coupled entities or data which could change over time. The examples of good implementation at the slide.

It is not good idea to use MongoDB in highly transaction systems, in systems with predefined model or in thightly coupled systems.


Thank you for your attention!