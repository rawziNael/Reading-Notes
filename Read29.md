# Read: 29 - Room  

# Content  

#### Save data in a local database using Room  

The Room persistence library acts as an abstraction layer over SQLite, allowing for fluent database access while still utilizing SQLite's full capability. Compile-time
SQL query verification, convenience annotations that reduce repetitious and error-prone boilerplate code, and simplified database migration pathways are all advantages
of Room.  

The database class is the main access point for the underlying connection to your app's persistent data, and it holds the database. Tables in the
database of your program are represented by data entities. Data access objects (DAOs) are objects that provide methods for querying, updating, inserting,
and deleting data in a database.  

AppDatabase is the app's main access point to the persistent data and determines the database settings. The database class has to meet the following requirements:
The @Database annotation must be added to the class, which contains an entities array that lists all of the database's data entities. The class must extend
RoomDatabase and be an abstract class. The database class must provide an abstract method with zero parameters that returns an instance of the DAO class for each
DAO class that is linked with the database.  

#### Defining data using Room entities  

You construct entities to represent the items you wish to save when you use the Room persistence library to store your app's data. Each entity in the linked Room
database corresponds to a table, and each instance of an entity represents a row of data in that table.  

The anatomy of a thing Each Room entity may be specified as a class with the @Entity annotation. A Room entity has fields for each column in the related database
table, as well as one or more primary key columns. The class name is used as the database table name in Room.  

Establish a primary key. Each Room object must have a primary key that identifies each row in the related database table in a unique way. The simplest method to
accomplish this is to use @PrimaryKey to annotate a single column. You may construct a composite primary key by listing those columns in the primaryKeys property
of @Entity if you require instances of an entity to be uniquely identifiable by a mix of numerous columns.  

Fields should be ignored. You may use @Ignore to annotate fields that you don't wish to persist in an entity, and ignoredColumns to annotate fields that an entity
inherits from a parent entity.  

Provide table search assistance. Room offers a variety of annotations that enable searching for information in your database's tables simpler. Add the @Fts3
or @Fts4 annotation to a specified object to enable full-text search. Include the indices property within the @Entity annotation, stating the names of the columns
you wish to include in the index or composite index, to add indices to an entity.  

Objects that are based on AutoValue should be included. Use Java-based immutable value classes, annotated with @AutoValue, as entities in your app's database
with Room. This feature comes in handy when two instances of an object are considered equal if their columns have the same values.  

You may use @PrimaryKey, @ColumnInfo, @Embedded, and @Relation to annotate the class's abstract methods with @AutoValue as entities. Include the @CopyAnnotations
annotation each time you use these annotations so that Room can properly comprehend the methods' auto-generated implementations.  

#### Define relationships between objects
Because SQLite is a relational database, relationships between entities may be specified.

Create embedded objects @Embedded annotation - indicates an item within a table that you want to deconstruct into its subfields. The embedded fields may then be
queried in the same way as other separate columns. If an object contains several embedded fields of the same type, you may use the prefix property to make each column
unique.  

A one-to-one connection is a relationship between two entities in which each instance of the parent entity corresponds to precisely one instance of the child entity
and vice versa. Model the one-to-one link between the two entities before querying the list of users and matching libraries. Create a new data class with each instance
containing an instance of the parent entity and the child entity's matching instance. The @Transaction annotation ensures that the entire process is completed in
a single step.  

A one-to-many connection exists when each instance of the parent entity relates to zero or more instances of the child entity, but each instance of the child entity
can only correspond to one instance of the parent object.  

A relationship between two entities in which each instance of the parent object corresponds to zero or more instances of the child entity, and vice versa, is known
as a many-to-many relationship. If you need to query a group of three or more tables that are all connected to each other, use nested relationships.  

#### Accessing data using Room DAOs
Data access objects (DOA) Each DAO has methods that provide abstract access to the database in your program. Room provides implementations of the DAOs you design
automatically at compile time.  

Each DAO can be specified as an interface or an abstract class.  

Use @Dao to annotate your DAOs.  

Convenience methods are SQL-free ways for inserting, updating, and deleting records in your database.  

Query methods allow you to interface with the database by writing your own SQL query.  

The @Insert annotation allows you to construct methods that insert their parameters into the database's relevant table.  

You may use the @Update annotation to construct methods for updating particular rows in a database table.  

The @Delete annotation lets you design methods for removing specific rows from a database table.  

The @Query annotation allows you to construct SQL queries that are then exposed as DAO methods.
