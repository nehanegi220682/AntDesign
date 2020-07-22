# INDEXING

# createIndex()
##### Creates index on required fields
## Syntax
    db.COLLECTION_NAME.createIndex( <key:1/-1>, <options>(optional) )
 key is the name of the field on which you want to create index and 1 is for ascending order.
 
#### Example
     db.studentdata.createIndex({student_name: 1})
#### Example
     db.mycol.createIndex({"title":1,"description":-1})
#### Example with Options
     db.studentdata.createIndex({student_name: 1}, {unique: true})
     
##### Other options values: background(create index in background), name(specify name for index)


# getIndex()
##### Find all the indexes created on a collection
## Syntax
    db.COLLECTION_NAME.getIndexes()
    
# Drop indexes   
##### Drop particular index or all indexes from collection
## Syntax
	db.collection_name.dropIndex({index_name: 1})
#### Example
	db.studentdata.dropIndex({student_name: 1})
### Dropping all the indexes:
	db.collection_name.dropIndexes()
	
# Index Types
### =>Single Field
### =>Compound Index
### =>Multikey Index
### =>Geospatial Index
### =>Text Indexes
### =>Hashed Indexes

# Single Field
##### sort order of the index key does not matter because MongoDB can traverse the index in either direction.

### Example
	db.studentdata.createIndex( { score: 1 } )
#### For embedded fields:
	db.studentdata.createIndex( { "location.state": 1 } )
	
# Compound Index
##### Compound indexes can support queries that match on multiple fields
## Syntax
	db.collection_name.createIndex( { <field1>: <type>, <field2>: <type2>, ... } )
	
### Example
	db.products.createIndex( { "item": 1, "stock": 1 } )
##### The order of the fields listed in a compound index is important

