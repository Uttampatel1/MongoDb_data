
🌟 MongoDB Cheat Sheet 🌟

📌 What is MongoDB? MongoDB is a popular document-oriented NoSQL database that provides high performance, scalability, and flexibility for handling large volumes of data. It stores data in flexible JSON-like documents, making it easy to model and retrieve complex data structures.

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
collection.update_many(query, new_values)` 
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

📌 Note: These are just a few basic operations. MongoDB offers a wide range of features and query capabilities. You can refer to the official MongoDB documentation for more detailed information: [https://docs.mongodb.com/](https://docs.mongodb.com/)

Happy coding! 🚀

ShareSave#   M o n g o D b _ d a t a  
 