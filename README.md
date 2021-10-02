# NoSQLConcepts

## Relational Databases vs NoSQL
| Relational Databases | NoSQL |
| --------------- | --------------- |
| Use tables/rows/columns | Don't Use tables/rows/columns | 
| Need a predefind schema / complicated to change structure | Schema less / easy change structure | 
| Slow queries when joining multiple tables | Fast queries | 
| Vertically scalable + More expernsive | Horizontal scalable + Cheaper | 
| Guarantee ACID transactions | Most don't support ACID transactions  | 


## Types of NoSQL Databases
- Key-value database
- Document database
- Column family database
- Graph database




## Key-value databases
- Such as map data structure
- Is a simplest NoSQL databases 
- Set / Get values with associated key

Key must be unique and not good option to have long keys because they will use more memory.


## Advantages of key-value databases
- Very simple
  - Key-value tuple
  - Not defined schema
  - Basic operations such as ```` Put````, ```` Get ```` and ```` Delete ````

- Very flexible
  - Allow changes in data type such as ```` User12 = 0111, User12 = "Giza" ````
  - Add additional attributes such as ```` User12 = {"lang": "en:US"}, User12 = {"lang": "en:US", "Color": "green"} ````
- Information stored in memory 
  - Fast read & write
- Scalability
  - Sharding => distributes different parts of the data accross multiple servers


## Limitations of key-value databases
- Just search by key  
  - Problem if we don't the key !!!!!!!!
  - Some key-value databases added functionalities to avoid this problem
    - Search by value
    - Add secondary index
    - Search by serveral key simultaneously
  - Not complex query 


## Suitable cases for value-key databases
- Shopping carts
  - Key => UserID
  - Value => shopping cart information

- Real time recommendations
  - Key => UserID
  - Value => items that user like it
 

The most popular key-value databases is **"Redis"**



------------------------------------------------------------------------------------------------------------------------------------------------------------


## Document Databases
- Schemaless
- Store data in documnets and these documents are grouped into collection
- If you are familiar with relational databases we can say documents are analogous to rows and collections are analogous to table


## Documents
- Set of key-value pairs
- Key: string
- Value: number, string, booleans, arrays, objects
- Polymorphic model it's means that documents within the same collection don't needt to have the same structure
- Formats: JSON, BSON, YAML, XML


## JSON document format
````
{  
  "user_id": 512,
  "name": "Carol", 
  "last_name": "Harper",
  "email": "carolharper@datazy.com",
  "address": { 
  "street": "123 Sesame Street",
  "city": "New York City", 
  "state": "New York",  
  "country": "USA"  },
  "hobbies": [   
  "hiking", "painting"
  ]
}

````

The value of "address" key is another document, notice that is related information is embedded in the main document, so don't need for searching about address in another document


## Collections
- Set of documents
- Store **the same type of entities**



## Advantages of document databases
- Flexibility
  - Don't need to predefine the schema
  - Documents can vary over time => avoid schema migrations 
  - Embedded documents => avoid joins
- Intuitive for developers
  - Natural way to work
  - JSON is human-readable
  - **Documents map objects** in code

- Horizontal scalability


## Limitations of document databases
- More responsibity
  - Care about data in the application code
  - Care about redundant data


The most popular document databases is **"Mogno DB"**

------------------------------------------------------------------------------------------------------------------------------------------------------------


## Column family database
- Derive from **Google BigTable**
- Store data in **column family**
    - Group related data together
- Also called **wide column databases** 
- Great when dealing with large volumes of data


## Structure 
- ![image](https://user-images.githubusercontent.com/64374947/135715654-7a8eb3c5-abcf-46b8-a69e-ff6d1c503fee.png)
- Row key: unique identifiers
- Each row can have differant number of columns


## Designing 
- Think about the queries
- No joins
  - Add all the column we need


## Advantages of Column family databases
- Flexibility
  - Rows within a column family can have **different columns**
  - Add new **columns** to a row if we need
  - **Avoid** filling with default value

- Speed
  - Related columns are **stored together on disk** 
  - **Very fast** writing / retriving

- Scalability
  - Scale horizontally

- Large volumes of data
  - Designed to **handle large volums of data*



## Limitation of Column family databases
- Atomic read / write **but no multirow transactions**
  - if you want to update in the same transaction a row that belongs to one column and then another row that belongs to another column family.

- No joins
- No subqueries
- Need to **define the queries quite well before modeling**
  - Query changes => modeling changes



## Suitable cases for Column family databases

- Large volumes of data
- Extreme write speeds


## Unsuitable cases for Column family databases
- Complex queries and joins
- Not deeling with large amounts of data

**Cassandra is one of the popular column-family databases**

------------------------------------------------------------------------------------------------------------------------------------------------------------



## Graph database
- Treat **data** and its **relationships** with the same importance
- based on graph theory


## Graph concepts
- Vertices / Nodes
- Edges / Links / arcs


## Node
- Represent **entities** such as users
- Have properties such as name, surname, email

## Edges
- Connect the nodes
- Define relationships between the nodes such as user1 **follows** user12
- Have properties such as  user1 follows user12 **since 2014** 


## Type of Edges
- Directed
  - Specific direction such as user1 ==> user12

- Undirected 
  - No direction it's means the relationships is mutual such as   user1 <==> user12

## Queries
- Traversing the graph such as get all the users that Ben follows 
- Path: Set of nodes and edges across a graph
- Query language: Cypher, Gremlin





























