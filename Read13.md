# Relationships in Spring Data REST  
we're going to take a look at how to work with relationships between entities in Spring Data REST.  
1- One-to-One Relationship  
```  
@Entity
public class Address {

    @Id
    @GeneratedValue
    private long id;

    @Column(nullable = false)
    private String location;

    @OneToOne(mappedBy = "address")
    private Library library;  
    ```
