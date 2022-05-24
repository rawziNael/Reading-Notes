# Read: 33 - GraphQL @connection

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

#### Has One relationship  

Create a one-directional one-to-one relationship between two models using the @hasOne directive.  

In the example below, a Project has a Team.  
```  
type Project @model {
  id: ID!
  name: String
  team: Team @hasOne
}

type Team @model {
  id: ID!
  name: String!
}  
```  

To customize the field to be used for storing the relationship information, set the fields array argument and matching it to a field on the type:   
```  
type Project @model {
  id: ID!
  name: String
  teamID: ID
  team: Team @hasOne(fields: ["teamID"])
}

type Team @model {
  id: ID!
  name: String!
}
```  

#### Has Many relationship  
Create a one-directional one-to-many relationship between two models using the @hasMany directive.  

```  
type Post @model {
  id: ID!
  title: String!
  comments: [Comment] @hasMany
}

type Comment @model {
  id: ID!
  content: String!
}  
```  

You can customize the specific secondary index used for the "has many" relationship. First, configure a secondary index using @index. Then, pass in the secondary index name indexName parameter and the respective fields which match the connected index.  

```  
type Post @model {
  id: ID!
  title: String!
  comments: [Comment] @hasMany(indexName: "byPost", fields: ["id"])
}

type Comment @model {
  id: ID!
  postID: ID! @index(name: "byPost", sortKeyFields: ["content"])
  content: String!
}  
```  

#### Belongs To relationship  

Make a "has one" or "has many" relationship bi-directional with the @belongsTo directive.  

```
type Project @model {
  id: ID!
  name: String
  team: Team @hasOne
}

type Team @model {
  id: ID!
  name: String!
  project: Project @belongsTo
}
```  

@belongsTo can be used without the fields argument. In those cases, a field is automatically generated to reference the parent’s primary key.  

#### Many-to-many relationship  

Create a many-to-many relationship between two models with the @manyToMany directive. Provide a common relationName on both models to join them into a many-to-many relationship.  

```  
type Post @model {
  id: ID!
  title: String!
  content: String
  tags: [Tag] @manyToMany(relationName: "PostTags")
}

type Tag @model {
  id: ID!
  label: String!
  posts: [Post] @manyToMany(relationName: "PostTags")
} 
```  

# CompletableFuture  

Java 8 introduced the CompletableFuture class. Along with the Future interface, it also implemented the CompletionStage interface. This interface defines the contract for an asynchronous computation step that we can combine with other steps.  

#### Using CompletableFuture as a Simple Future  
The CompletableFuture class implements the Future interface, so we can use it as a Future implementation, but with additional completion logic.  

``` 
public Future<String> calculateAsync() throws InterruptedException {
CompletableFuture<String> completableFuture = new CompletableFuture<>();

    Executors.newCachedThreadPool().submit(() -> {
        Thread.sleep(500);
        completableFuture.complete("Hello");
        return null;
    });

    return completableFuture;
}
```  

#### CompletableFuture with Encapsulated Computation Logic  

Static methods runAsync and supplyAsync allow us to create a CompletableFuture instance out of Runnable and Supplier functional types correspondingly , Both Runnable and Supplier are functional interfaces that allow passing their instances as lambda expressions thanks to the new Java 8 feature.  

```
CompletableFuture<String> future
= CompletableFuture.supplyAsync(() -> "Hello");

// ...
assertEquals("Hello", future.get());
```  

#### Processing Results of Asynchronous Computations
The thenApply method does exactly that; it accepts a Function instance, uses it to process the result, and returns a Future that holds a value returned by a function.

``` 
CompletableFuture<String> completableFuture
= CompletableFuture.supplyAsync(() -> "Hello");

CompletableFuture<String> future = completableFuture
.thenApply(s -> s + " World");

assertEquals("Hello World", future.get());
``` 
