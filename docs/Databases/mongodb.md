# MongoDB Cheatsheet

## Basics

### 1. **Installation and Startup:**

- **Install MongoDB**: Depending on your operating system, the installation process may vary. For macOS users, Homebrew is a convenient option, but official MongoDB packages are also available for download on the MongoDB website.
- **Start MongoDB**: Once installed, you can start MongoDB with the `mongod` command. If you need to specify a different data directory, use the `--dbpath` option.

- Install MongoDB: `brew install mongodb` (on macOS using Homebrew)
- Start MongoDB: `mongod`

### 2. **MongoDB Shell:**

- **Enter the MongoDB shell**: The `mongo` command will open an interactive shell connected to your running MongoDB instance.
- **Exit the MongoDB shell**: Simply type `exit` to leave the shell.

- Enter the MongoDB shell: `mongo`
- Exit the MongoDB shell: `exit`

### 3. **Databases:**

- **Create/select a database**: The `use` command will either switch to an existing database or create a new one if the specified database doesn’t exist.
- **Drop a database**: This command will permanently delete the current database along with all its collections and data.

- Show all databases: `show dbs`
- Create/select a database: `use <database_name>`
- Drop a database: `db.dropDatabase()`

### 4. **Collections:**

- **Create a collection**: MongoDB can create collections automatically when you insert data, but you can also create empty collections with `db.createCollection()`.
- **Drop a collection**: This command will permanently delete the specified collection and all the data in it.

- Show all collections: `show collections`
- Create a collection: `db.createCollection("<collection_name>")`
- Drop a collection: `db.<collection_name>.drop()`

### 5. **CRUD Operations:**

- **Create**:
  - **Insert documents**: You can insert single or multiple documents into a collection with `insertOne()` or `insertMany()` respectively.
- **Read**:
  - **Find documents**: Use the `find()` method to retrieve documents from a collection. You can pass a query object to filter the results.
- **Update**:
  - **Update documents**: The `updateOne()` and `updateMany()` methods allow you to modify documents in a collection based on a query.
- **Delete**:
  - **Delete documents**: Use `deleteOne()` or `deleteMany()` to remove documents from a collection based on a query.

- **Create:**
  - Insert one document: `db.<collection_name>.insertOne({<document>})`
  - Insert multiple documents: `db.<collection_name>.insertMany([{<document_1>}, {<document_2>}, ...])`

- **Read:**
  - Find all documents: `db.<collection_name>.find()`
  - Find specific documents: `db.<collection_name>.find({<query>})`

- **Update:**
  - Update one document: `db.<collection_name>.updateOne({<query>}, {<update>})`
  - Update multiple documents: `db.<collection_name>.updateMany({<query>}, {<update>})`

- **Delete:**
  - Delete one document: `db.<collection_name>.deleteOne({<query>})`
  - Delete multiple documents: `db.<collection_name>.deleteMany({<query>})`

### 6. **Indexing:**

- **Create an index**: Indexes are crucial for query performance. Use `createIndex()` to create an index on a specific field in a collection.

- Create an index: `db.<collection_name>.createIndex({<field>: <direction>})`

### 7. **Aggregation:**

- **Basic aggregation**: The `aggregate()` method allows you to process data records and return computed results.

- Basic aggregation: `db.<collection_name>.aggregate([{<stage>}, ...])`

### 8. **Backup and Restore:**

- **Backup**: Use `mongodump` to create a binary export of the contents of a database.
- **Restore**: Use `mongorestore` to restore data from a binary database dump.

- Backup: `mongodump --db <database_name> --out <directory>`
- Restore: `mongorestore --db <database_name> <directory>`

### 9. **Monitoring and Performance Tuning:**

- **Get server status**: The `db.serverStatus()` command returns a document that provides an overview of the database’s state.
- **Explain a query**: The `explain()` method returns information about how MongoDB executed a query.

- Get server status: `db.serverStatus()`
- Get database stats: `db.stats()`
- Explain a query: `db.<collection_name>.find({<query>}).explain()`

### 10. **Miscellaneous:**

- **Show current database**: The `db` command will print the name of the current database.
- **Get list of commands**: The `db.help()` command will provide a list of all available commands in the MongoDB shell.

- Show current database: `db`
- Get list of commands: `db.help()`

### Querying in MongoDB

1. **Basic Queries**:
   - **Find All Documents in a Collection**:
     - Syntax: `db.<collection_name>.find()`

    ```js
    db.<collection_name>.find()
    ```

   - **Find Specific Documents**:
     - Syntax: `db.<collection_name>.find({<field>: <value>})`
     - Example: `db.users.find({age: 25})` finds all documents in the `users` collection where the `age` field has a value of `25`.
   - Find All Documents in a Collection:

    ```js
    db.<collection_name>.find({<field>: <value>})
    db.users.find({age: 25})
    ```

2. **Query Operators**:
   MongoDB supports a variety of operators for more complex queries.
   - **Comparison Operators**:
     - `$gt`: Greater than
     - `$gte`: Greater than or equal to
     - `$lt`: Less than
     - `$lte`: Less than or equal to
     - Example: `db.users.find({age: {$gt: 25}})` finds all documents where `age` is greater than `25`.

   - Greater Than ($gt):

    ```js
    db.<collection_name>.find({<field>: {$gt: <value>}})

    db.users.find({age: {$gt: 25}})
    ```

   - Less Than ($lt):

    ```js
    db.<collection_name>.find({<field>: {$lt: <value>}})

    db.users.find({age: {$lt: 25}})
    ```

   - **Logical Operators**:
     - `$and`: Logical AND
     - `$or`: Logical OR
     - Example: `db.users.find({$or: [{age: 25}, {name: 'John'}]})` finds all documents where `age` is `25` or `name` is `John`.
     - AND:

        ```js
        db.<collection_name>.find({<field1>: <value1>, <field2>: <value2>})

        db.users.find({age: 25, name: "John"})
        ```

     - OR:

        ```js
        db.<collection_name>.find({$or: [{<field1>: <value1>}, {<field2>: <value2>}]})

        db.users.find({$or: [{age: 25}, {name: "John"}]})
        ```

3. **Projection**:
   Projection is used to include or exclude fields from the result set.
   - Syntax: `db.<collection_name>.find({<query>}, {<field>: <0 or 1>})`
   - Example: `db.users.find({}, {name: 1, age: 1})` retrieves only the `name` and `age` fields from the `users` collection.
   - Selecting Specific Fields:

    ```js
    db.<collection_name>.find({}, {<field1>: 1, <field2>: 1})

    db.users.find({}, {name: 1, age: 1})  // Only returns the 'name' and 'age' fields
    ```

4. **Limit, Skip, and Sort**:
   - **Limit**: Limits the result set to a specific number of documents.
     - Syntax: `db.<collection_name>.find().limit(<number>)`
     - Example: `db.users.find().limit(5)` retrieves the first 5 documents.
   - **Skip**: Skips a specific number of documents.
     - Syntax: `db.<collection_name>.find().skip(<number>)`
     - Example: `db.users.find().skip(5)` skips the first 5 documents.

    ```js
    db.<collection_name>.find().skip(<number>)

    db.users.find().skip(10)  // Skips
    ```

   - **Sort**: Sorts the result set based on specified criteria.
     - Syntax: `db.<collection_name>.find().sort({<field>: <1 or -1>})`
     - Example: `db.users.find().sort({name: 1})` sorts the documents in ascending order by `name`.

    ```js
    db.<collection_name>.find().sort({<field>: <direction>})

    db.users.find().sort({age: 1})  // Sorts by age in ascending order
    ```

5. **Count**:
   - Syntax: `db.<collection_name>.find({<query>}).count()`
   - Example: `db.users.find({age: {$gt: 25}}).count()` counts the number of documents where `age` is greater than `25`.

6. **Regex**:
   - MongoDB supports regular expression searches.
   - Syntax: `db.<collection_name>.find({<field>: /<regex>/})`
   - Example: `db.users.find({name: /John/})` finds all documents where the `name` field contains the substring "John".
   - Pattern Matching:

    ```js
    db.<collection_name>.find({<field>: /pattern/})

    db.users.find({name: /Jo/})  // Finds all names containing the substring "Jo"
    ```

7. **Aggregation**:
   - MongoDB provides a powerful aggregation framework to process data and return computed results.
   - Syntax: `db.<collection_name>.aggregate([{<stage>}, ...])`
   - Example: `db.sales.aggregate([{ $group: { _id: "$item", total: { $sum: "$amount" }}}])` groups documents by `item` and calculates the total amount for each item.

These are some of the basics of querying in MongoDB. There are many more operators and techniques available for more complex queries. It's recommended to check the [official MongoDB documentation](https://docs.mongodb.com/manual/tutorial/query-documents/) for a deeper dive into querying and other advanced topics.
