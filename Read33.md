# Data modeling
Amplify automatically creates Amazon DynamoDB database tables for GraphQL types annotated with the @model directive in your GraphQL schema. You can create relations
between the data models via the @hasOne, @hasMany, @belongsTo, and @manyToMany directives.  

#### Setup database tables  
The following GraphQL schema automatically creates a database table for "Todo".  
```
type Todo @model {
  content: String
}  
```  

The Amplify CLI generates the Todo database table upon amplify push and generates a GraphQL API to perform create, read, update, delete, and list operations for the
Todo model.  

#### Configure a primary key  
Every GraphQL type with the @model directive will automatically have an id field set as the primary key.  
```  
type Todo @model {
  todoId: ID! @primaryKey
  content: String
}
```  

#### Configure a secondary index  

Amplify uses Amazon DynamoDB tables as the underlying data source for @model types. For key-value databases, it is critical to model your access patterns with "secondary
indexes". Use the @index directive to configure a secondary index.  

```  
type Customer @model {
  id: ID!
  name: String!
  phoneNumber: String
  accountRepresentativeID: ID! @index(name: "byRepresentative", queryField: "customerByRepresentative")
}  
```  

#### Setup relationships between models  

Create "has one", "has many", "belongs to", and "many to many" relationships between @model types.  

| Relationship | Description |
| ----------- | ----------- |
| @hasOne | Create a one-directional one-to-one relationship between two models. For example, a Project "has one" Team. This allows you to query the team from the project record. |
| @hasMany |Create a one-directional one-to-many relationship between two models. For example, a Post has many comments. This allows you to query all the comments from the post record. |
| @belongsTo |Use a "belongs to" relationship to make a "has one" or "has many" relationship bi-directional. For example, a Project has one Team and a Team belongs to a Project. This allows you to query the team from the project record and vice versa. |
| @manyToMany |Configures a "join table" between two models to facilitate a many-to-many relationship. For example, a Blog has many Tags and a Tag has many Blogs. |  





