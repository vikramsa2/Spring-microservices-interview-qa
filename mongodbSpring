Adding Dependencies
Add the below dependencies in the pom.xml file.

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-mongodb</artifactId>
</dependency>
<dependency>
     <groupId>org.springframework.boot</groupId>
     <artifactId>spring-boot-starter-web</artifactId>
</dependency>


Purpose of this Dependencies:

spring-boot-starter-data-mongodb: This dependency brings in all the necessary components to work with MongoDB in a Spring Boot application. As name mention it is a starter which means if we don't include this than we have to do so many configuration to work with mongoDb which this package can give us before. Importantly this package gives us so many things including Repositories support, Mapping and Querying with databases.
spring-boot-starter-web: This dependency sets up the foundation for building web applications, including RESTful services, using Spring MVC (Model-View-Controller) and embedded web servers. This will give us the paradigm for working with APIs.

MongoDB Connection Properties:
There is some important parameter we need to know to connect the MongoDB server with Spring Boot.

Port (By Default Port - 27017)
Host (By Default Host - localhost)
Database Name 
Credential (Optional)


spring.data.mongodb.host=localhost
spring.data.mongodb.port=27017
spring.data.mongodb.database=demo
spring.data.mongodb.username=username_value  (optional)
spring.data.mongodb.password=password_value (optional)


------------------------------------------------------------------------------------------

Step 1: Create the "User" Class
Create a User class and annotate it with @Document. This class will represent your MongoDB document.


import org.springframework.data.annotation.Id;
import org.springframework.data.mongodb.core.mapping.Document;

@Document
public class User {
    @Id
    private String userId;
    private String name;
    private String rollNumber;
    
    public User(String name, String rollNumber) {
        super();
        this.name = name;
        this.rollNumber = rollNumber;
    }
    public String getUserId() {
        return userId;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public String getRollNumber() {
        return rollNumber;
    }
    public void setRollNumber(String rollNumber) {
        this.rollNumber = rollNumber;
    }
}

Step 2: Create the Repository Interface
import org.springframework.data.mongodb.repository.MongoRepository;

public interface UserRepository extends MongoRepository<User,String>{

}

Step 3: Create the Controller Class
Now this is the final step in this step we will create the controller class from there we will perform CRUD operation in our database.

We annotate the controller class with @RestController.
We create an object of our repository and annotate it with @Autowired.

Code :

import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestBody;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class UserController {
    
    @Autowired 
    private UserRepository userRepo;
    
    // Save method is predefine method in Mongo Repository
    // with this method we will save user in our database
    @PostMapping("/addUser")
    public User addUser(@RequestBody User user) {
        return userRepo.save(user);
    }
    
    // findAll method is predefine method in Mongo Repository 
    // with this method we will all user that is save in our database
    @GetMapping("/getAllUser")
    public List<User> getAllUser(){
        return userRepo.findAll(); 
    }
}
------------------------

How to connecting multiple database in spring boot
Connecting to multiple databases in a Spring Boot application involves configuring multiple DataSource beans, each representing a connection to a different database. Here's a breakdown of the process:

1. Define Configuration Properties:
In your application.properties or application.yml file, define separate properties for each database, including URL, username, password, and driver class.
Use distinct prefixes for each database configuration (e.g., spring.datasource.primary, spring.datasource.secondary).

// Config

# MySQL DataSource Configuration
spring.datasource.mysql.jdbc-url=jdbc:mysql://localhost:3306/mysqldb
spring.datasource.mysql.username=root
spring.datasource.mysql.password=password
spring.datasource.mysql.driver-class-name=com.mysql.cj.jdbc.Driver

# PostgreSQL DataSource Configuration
spring.datasource.postgresql.jdbc-url=jdbc:postgresql://localhost:5432/postgresdb
spring.datasource.postgresql.username=postgres
spring.datasource.postgresql.password=password
spring.datasource.postgresql.driver-class-name=org.postgresql.Driver


@Configuration
public class DataSourceConfig {

@Primary <-- This main annontion
@Bean(name = “firstDataSource”)
@ConfigurationProperties(prefix = “spring.datasource.first”)
public DataSource firstDataSource() {
return DataSourceBuilder.create().build();
}

@Bean(name = “secondDataSource”)
@ConfigurationProperties(prefix = “spring.datasource.second”)
public DataSource secondDataSource() {
return DataSourceBuilder.create().build();
}
}
