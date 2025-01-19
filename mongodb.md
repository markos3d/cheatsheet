# MongoDB Basics
- `show dbs` - List all databases
- `use shop` - Switch to/create database
- `cls` - Clear screen
- `mongo --port 27018` - Connect to custom port

# CRUD Operations
## Create
- `db.collection.insertOne({field: value})`
- `db.collection.insertMany([{}, {}])`

## Read
- `db.collection.find()` - Get all (first 20)
- `db.collection.find().pretty()` - Formatted view
- `db.collection.find({field: value})` - Filter
- `db.collection.find({}, {name: 1})` - Projection

## Update
- `db.collection.updateOne({filter}, {$set: {field: value}})`
- `db.collection.updateMany({}, {$set: {field: value}})`
- `db.collection.replaceOne({filter}, {newDoc})`

## Delete
- `db.collection.deleteOne({filter})`
- `db.collection.deleteMany({filter})`

# Query Operators
- `$lt` - Less than
- `$gt` - Greater than
- `$set` - Set value

# Tips
- Embedded docs: `status.description`
- Arrays: Can store any data type
- ObjectId: Auto-generated `_id`
- Find in arrays: `db.collection.find({array: 'value'})`

# Admin Commands
- `db.stats()` - Database stats
- `db.dropDatabase()` - Delete database
- `db.help()` - Show commands
- `mongoimport file.json -d db -c collection`

# Server Management
- Custom config: `mongod --config path/mongod.cfg`
- Background: `mongod --fork`
- Stop: `use admin` then `db.shutdownServer()`
