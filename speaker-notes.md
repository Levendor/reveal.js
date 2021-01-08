Welcome to MongoDB introducing presentation. Today i will give you a basic information of MongoDB database, its definitions, short history, architecture and features. Lets start from brief MongoBD story.

The history of MongoDB started in 2007 from a company called 10gen. 10gen began developing MongoDB as a component of a planned platform as a service product.
Development on the new database was carried out from 2007 to 2009. The core engine was written in C++. The database was named MongoDB, since the idea was to use it to store and serve humongous amount of data, required in typical use cases, such as content serving.
The developer team decided to focus just on the MongoDB database, instead of the initial service product. The business idea was to release the database as an open source free download, and offer commercial support and training services.
MongoDB version 1 was released in February 2009.

At this slide you can see the major milestones of MongoDB evolution.
Realising the true business potential, 10gen was renamed as MongoDB Inc. in 2013 to focus on the database product.
One of the major problems with early MongoDB was its relatively weak storage engine, used for saving and managing the data on the disk. The company's first acquisition was WiredTiger, a project behind the super stable storage engine with the same name.

Next major release of MongoDB was version 3 at March 2015, which featured the new WiredTiger storage engine.
In 2018, the company went for its second acquisition by taking over mLab for 68 million dollars. At the time mLab was providing MongoDB as a service on the cloud, and had a large number of customers. Cloud was the future, and MongoDB Inc. moved quickly to acquire and integrate mLab as part of the MongoDB Atlas cloud platform.

MongoDB is a document based NoSQL database. It can run on all major platforms (Windows, Linux and Macintosh). The open source version is available as a free download. MongoDB stores data entities in a container, called collection, and each piece of data is stored in a JSON document format.
MongoDB also comes with a console client called MongoDB shell. This is a JavaScript environment using which you can add, remove, edit or query document data in the database.

A NoSQL database (originally referring to "non-SQL" or "non-relational") provides a mechanism for storage and retrieval of data, that is modeled in means, other than the tabular relations used in relational databases.
The data structures used by NoSQL databases (such as key–value pair, wide column, graph, or document) are different from those, used by default in relational databases, making some operations faster in NoSQL.

A document-oriented database is a specialized key-value store, which is another NoSQL database category. In a simple key-value store, the document content is not transparent. A document-oriented database provides APIs, that exposes the ability to query or update, based on the internal structure in the document.
A key difference between the document-oriented and relational models, is that the data formats are not predefined in the document case.
Relational databases generally store data in separate tables, that are defined by the programmer, and a single object may be spread across several tables.
Document databases store all information for a given object in a single instance in the database, and every stored object can be different from every other.

BSON, short for Bin­ary JSON, is a bin­ary-en­coded serialization of JSON-like documents.
BSON is designed to be efficient in space, but in some cases uses even more space than JSON. The reason for this is another of the BSON design goals: traversability. BSON adds some "extra" information to documents, like length of strings and sub-objects. This makes traversal faster.
BSON is also designed to be fast to encode and decode. For example, integers are stored in integer data format, so they don't need to be parsed to and from text. This uses more space than JSON for small values, but is much faster to parse.
In addition to compactness, BSON adds additional data types, unavailable in JSON, notably the BinData and Date data types.

The following MongoDB architecture diagram provides the major components in the MongoDB server.

MongoDB currently offers drivers for 13 languages including Java, Node.JS, Python, PHP and Swift.
MongoDB ships with three supported storage engines, all of which can coexist within a single MongoDB replica set:

The default WiredTiger storage engine
The Encrypted storage engine, protecting highly sensitive data. (Requires MongoDB Enterprise Advanced)
The In-Memory storage engine, delivering the extreme performance and real time analytics for the most demanding, latency-sensitive applications. (This is also requires enterprise version)
The MMAP version 1 engine, that was used only before 4.2 release.


Now lets talking about MongoDB features.

Aggregation: A MongoDB server contains databases, each of which is a physical container for collections. Each collection is a group of documents. Now, a document is a set of key-value pairs that has a dynamic schema. That means all documents in one collection might not have the same structure, and the common fields in documents might contain different data types.
Document-oriented: The document structure is more similar with that, how developers create their classes and objects in their programming languages. Developers often say, that the classes are not in rows and columns, but have a structure as key-value pairs.
Schema-less Database: In NoSQL databases, the documents don’t need to have a schema, that is defined beforehand. The MongoDB data modelling allows you to represent hierarchical relationships, to store arrays and other complex structures.
Grid File System: For storing and retrieving large files GridFS is used in Mongo. GridFS is a file system that only stores the files, and their data is stored within MongoDB collections. GridFS can store files, greater than its document size, within the limit of 16 MB.


Another important feature is that it supports MapReduce and aggregation tools.
The "map" operation can write results to a collection. If you perform the subsequent "reduce" operation on the same input collection, then it merges, or replaces, or reduces the new results with the previous results.
MapReduce can be used for aggregation operations. When large datasets process and generate results with the help of parallel and distributed algorithms on clusters, it is called MapReduce.


MongoDB uses BSON while storing documents in collections
As a primary key, the BSON format uses "_id" field. As "_id" is used as a primary key, it should have a unique value, associated with it, which is called ObjectId, generated automatically.
There are many other advantages of using the BSON format, such as it enables internal index and map document properties. Also, it increases the read/write throughput of MongoDB.

MongoDB provides sharding to overcome scaling problem of web or mobile application. Sharding is a method, in which data is distributed across multiple machines. With the help of sharding, it is able to offer horizontal scalability.
Sharding is a complicated process, and is done with the help of several shards. Each shard holds some part of the data as a separate database. Merging all the shards together forms a single logical database.

MongoDB supports range query, regular expression and other types of searches. The queries include user-defined JavaScript functions, and they return specific fields from the documents. By indexing BSON documents, it can support ad-hoc queries.
At the slide you can see the difference between a SQL query and a MongoDB query, by checking how to fetch all the records from a table for the employee name ‘XYZ’ in both databases.

MongoDB index is used to improve the performance of searches. Any field in a MongoDB document can be indexed as either primary or secondary. This lets the database engine to efficiently resolve the queries.

On the other hand, there are still areas where MongoDB doesn’t perform as well as other databases. Here are some of the downsides of MongoDB:

Joins
Joining documents in MongoDB is no easy task, and though version 3.2 introduced joins, developers are still working on the function and it’s not quite mature yet. Pulling data from several collections requires a number of queries, which will lead to messy code and long turn-around times.
Indexing
Quick speeds and high performance is only possible with the right indexes. With badly implemented and out of order composite indexes, MongoDB will operate at a very slow speed.
Duplicates
Some of these downsides could lead to duplicate data. The relationships in MongoDB are not typically well-defined, and the resulting duplicate data sets can be hard to handle. That, along with not being ACID compliant, would lead to corrupted data.

It is good to implement MongoDB for:

E-commerce product catalog.
Blogs and content management.
Real-time analytics and high-speed logging and caching.
Configuration management.
Maintaining geospatial data.
Mobile and social networking sites.
Evolving data requirements.
Loosely coupled objectives — the design may change by over time.


However, MongoDB is not so good for:

Highly transactional systems or where the data model is designed beforehand.
Tightly coupled systems


Thank you for your attention!