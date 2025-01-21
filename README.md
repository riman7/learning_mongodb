# Mongodb
MongoDB is a NoSQL database management system designed to store and manage large volumes of data in a flexible, document-oriented manner. Unlike traditional relational databases, MongoDB uses a non-tabular format, making it ideal for applications that require scalability and high-performance data processing. 

## **Getting Started**

Before using the commands below, make sure:
1. MongoDB is installed and running on your machine or server.
2. You have connected to MongoDB using the `mongo` shell or a driver.

---

## **Database Commands**  
Any Database contains "CRUD" operation
- Create
- Read
- Update
- Delete

### 1. **Show Databases**
```shell
show dbs
```
Lists all databases.

### 2. **Switch/Create Database**
```shell
use database_name
```
Switches to the specified database. If it does not exist, MongoDB creates it when you insert data.

### 3. **Drop Database**
```shell
db.dropDatabase()
```
Deletes the current database.

---

## **Collection Commands**

### 1. **Show Collections**
```shell
show collections
```
Lists all collections in the current database.

### 2. **Create Collection**
```shell
db.createCollection("collection_name")
```
Creates a new collection.

### 3. **Drop Collection**
```shell
db.collection_name.drop()
```
Deletes the specified collection.

---

## **CRUD Operations**

### 1. **Insert Documents**

#### Insert One Document
```shell
db.collection_name.insertOne({ key: "value" })
```

#### Insert Multiple Documents
```shell
db.collection_name.insertMany([
  { key1: "value1" },
  { key2: "value2" }
])
```

### 2. **Query Documents**

#### Find All Documents
```shell
db.collection_name.find()
```

#### Find Documents with a Condition
```shell
db.collection_name.find({ key: "value" })
```

#### Find with Projections
```shell
db.collection_name.find({ key: "value" }, { key_to_include_or_exclude: 1 })
```

#### Find One Document
```shell
db.collection_name.findOne({ key: "value" })
```

### 3. **Update Documents**

#### Update One Document
```shell
db.collection_name.updateOne(
  { key: "value" },
  { $set: { updated_key: "new_value" } }
)
```

#### Update Multiple Documents
```shell
db.collection_name.updateMany(
  { key: "value" },
  { $set: { updated_key: "new_value" } }
)
```

### 4. **Delete Documents**

#### Delete One Document
```shell
db.collection_name.deleteOne({ key: "value" })
```

#### Delete Multiple Documents
```shell
db.collection_name.deleteMany({ key: "value" })
```

---

## **Indexing Commands**

### 1. **Create Index**
```shell
db.collection_name.createIndex({ key: 1 })
```
`1` for ascending and `-1` for descending order.

### 2. **Show Indexes**
```shell
db.collection_name.getIndexes()
```

### 3. **Drop Index**
```shell
db.collection_name.dropIndex("index_name")
```

---

## **Aggregation Commands**

### 1. **Basic Aggregation Pipeline**
```shell
db.collection_name.aggregate([
  { $match: { key: "value" } },
  { $group: { _id: "$key", total: { $sum: "$numeric_field" } } }
])
```

---

## **Administrative Commands**

### 1. **View Current Database Stats**
```shell
db.stats()
```

### 2. **View Collection Stats**
```shell
db.collection_name.stats()
```

### 3. **Compact Collection**
```shell
db.runCommand({ compact: "collection_name" })
```

---

This README covers the fundamental commands to get started with MongoDB. For more advanced operations, refer to the [official MongoDB documentation](https://www.mongodb.com/docs/).
