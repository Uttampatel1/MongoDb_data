🌟 MongoDB Cheat Sheet 🌟

📌 What is MongoDB? 
-   MongoDB is a popular document-oriented NoSQL database that provides high performance, scalability, and flexibility for handling large volumes of data. It stores data in flexible JSON-like documents, making it easy to model and retrieve complex data structures.

📌 Use cases of MongoDB:

-   Content Management Systems (CMS) 📄: MongoDB is well-suited for storing and managing content due to its flexible schema and ability to handle unstructured data.
-   Real-time Analytics 📊: MongoDB's ability to handle large volumes of data with high throughput makes it a good choice for real-time analytics applications.
-   Internet of Things (IoT) 🌐: MongoDB can efficiently store and process data from various IoT devices due to its scalability and ability to handle large amounts of data.
-   Catalogs and Product Data 🛍️: MongoDB's document model is ideal for storing and retrieving product data, making it suitable for e-commerce platforms.
-   Mobile Applications 📱: MongoDB's support for offline synchronization and mobile-specific features makes it a good fit for mobile app development.


📌 How to use MongoDB in Python: To use MongoDB in Python, follow these steps:

    Step 1️⃣: Install the MongoDB Python driver using pip:

    ```code
    pip install pymongo
    ```

    Step 2️⃣: Import the pymongo library in your Python script:

    ```code
    import pymongo
    ```

    Step 3️⃣: Establish a connection to the MongoDB server:

        ```
        # Replace "mongodb://localhost:27017" with your MongoDB connection string
        client = pymongo.MongoClient("mongodb://localhost:27017")
        ``` 

    Step 4️⃣: Access a database and collection:
        
        ``` 
        # Access a specific database
        db = client["mydatabase"]
        
        # Access a specific collection within the database
        collection = db["mycollection"]
        ```

    Step 5️⃣: Perform database operations:

    -   Insert documents 📥:
        ```
        # Insert a single document
        document = {"name": "John", "age": 30}
        collection.insert_one(document)
        
        # Insert multiple documents
        documents = [
            {"name": "Alice", "age": 25},
            {"name": "Bob", "age": 35}
        ]
        collection.insert_many(documents)
        ```

    -   Find documents 🔍:

        ```
        # Find all documents in a collection
        result = collection.find()
        
        # Find documents that match a specific query
        query = {"name": "John"}
        result = collection.find(query)
        
        # Iterate over the result
        for document in result:
            print(document)
        ```

    -   Update documents ✏️:

            ```
            # Update a document
            query = {"name": "John"}
            new_values = {"$set": {"age": 40}}
            collection.update_one(query, new_values)
            
            # Update multiple documents
            query = {"age": {"$lt": 30}}
            new_values = {"$inc": {"age": 1}}
            collection.update_many(query, new_values)
            ```
    -   Delete documents ❌:
        ```
        # Delete a document
        query = {"name": "John"}
        collection.delete_one(query)
        
        # Delete multiple documents
        query = {"age": {"$gt": 40}}
        collection.delete_many(query)
        ```

## MongoDB query operators in PyMongo

1.  Comparison Operators:
    -   `$eq` (Equals): Matches values that are equal to a specified value. ✅
    -   `$ne` (Not Equals): Matches values that are not equal to a specified value. ❌
    -   `$gt` (Greater Than): Matches values that are greater than a specified value. ⬆️
    -   `$lt` (Less Than): Matches values that are less than a specified value. ⬇️
    -   `$gte` (Greater Than or Equal): Matches values that are greater than or equal to a specified value. ⬆️🔳
    -   `$lte` (Less Than or Equal): Matches values that are less than or equal to a specified value. ⬇️🔳

2.  Logical Operators:
    
    -   `$and` (Logical AND): Joins query clauses with a logical AND and returns documents that match all conditions. 👥✅
    -   `$or` (Logical OR): Joins query clauses with a logical OR and returns documents that match any condition. 👥🔀
    -   `$not` (Logical NOT): Inverts the effect of a query expression and returns documents that do not match the condition. 🚫
    -   `$nor` (Logical NOR): Joins query clauses with a logical NOR and returns documents that do not match any condition. 👥🚫

3.  Element Operators:
    
    -   `$exists` (Field Exists): Matches documents that have the specified field. ✅❓
    -   `$type` (Field Type): Matches documents where the value of the field is of the specified BSON type. 🔢🔳

4.  Array Operators:

    -   `$in` (Value In Array): Matches any of the values specified in an array. ✔️🔢
    -   `$nin` (Value Not in Array): Matches none of the values specified in an array. ❌🔢
    -   `$all` (All Values in Array): Matches arrays that contain all the specified elements. ✔️🔢🔳

5.  Update Operators:
    
    -   `$set` (Set Field): Sets the value of a field in an update operation. 🖋️✅
    -   `$unset` (Unset Field): Removes a field from a document. 🖋️❌
    -   `$inc` (Increment Field): Increments the value of a field by a specified amount. ➕🖋️
    -   `$push` (Push Value to Array): Appends a value to an array field. ➕🔢🖋️
    -   `$pull` (Pull Value from Array): Removes all instances of a value from an array field. ➖🔢🖋️
    -   `$addToSet` (Add Unique Value to Set): Adds elements to an array field only if they do not already exist. ➕🔢🔒

6.  Projection Operators:

    -   `$project` (Field Projection): Specifies the fields to include or exclude in the query result. 📊🔳
    -   `$slice` (Array Slice): Limits the number of elements returned in an array field. 📊🔢
    
📌 Note: These are just a few basic operations. MongoDB offers a wide range of features and query capabilities. You can refer to the official MongoDB documentation for more detailed information: [https://docs.mongodb.com/](https://docs.mongodb.com/)


📌  These operators allow for powerful querying and updating of MongoDB documents using PyMongo. For detailed information on these operators and their usage, refer to the official MongoDB documentation: [https://docs.mongodb.com/manual/reference/operator/](https://docs.mongodb.com/manual/reference/operator/)