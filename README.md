# NoSQLConcepts

## Relational Databases vs NoSQL
| Relational Databases | NoSQL |
| --------------- | --------------- |
| Use tables/rows/columns | Don't Use tables/rows/columns | 
| Need a predefind schema / complicated to change structure | schema less / easy change structure | 
| Slow queries when joining multiple tables | Fast queries | 
| Vertically scalable + More expernsive | horizontal scalable + Cheaper | 
| Guarantee ACID transactions | Most don't support ACID transactions  | 


## Types of NoSQL Databases
- key-value database
- Document database
- Column family database
- Graph database




## Key-value databases
- such as map data structure
- is a simplest NoSQL databases 
- Set / Get values with associated key

Key must be unique and not good option to have long keys because they will use more memory.


## Advantages of key-value databases
- very simple
  - key-value tuple
  - Not defined schema
  - Basic operations such as Put, Get and Delete

- very flexible
  - Allow changes in data type such as ```` User12 = 0111, User12 = "Giza" ````
  - Add additional attributes such as ```` User12 = {"lang": "en:US"}, User12 = {"lang": "en:US", "Color": "green"} ````
- Information stored in memory 
  - ast read & write
- Scalability
  - Sharding => distributes different parts of the data accross multiple servers


## Limitations of key-value databases
- Just search by key  
  - Problem if we don't the key !!!!!!!!
  - some key-value databases added functionalities to avoid this problem
    - search by value
    - add secondary index
    - search by serveral key simultaneously
  - Not complex query 


## Suitable cases for value-key databases
- Shopping carts
  - Key => UserID
  - value => shopping cart information

- Real time recommendations
  - Key => UserID
  - value => items that user like it













