1) What is hibernate?
Hibernate is an open-source and lightweight ORM tool that is used to store, manipulate, and retrieve data from the database.

2) What is ORM?
ORM is an acronym for Object/Relational mapping. It is a programming strategy to map object with the data stored in the database. It simplifies data creation, data manipulation, and data access.

Explain hibernate architecture?
Hibernate architecture comprises of many interfaces such as Configuration, SessionFactory, Session, Transaction, etc.

The Hibernate architecture includes many objects such as persistent object, session factory, transaction factory, connection factory, session, transaction etc.

 
The Hibernate architecture is categorized in four layers.

Java application layer
Hibernate framework layer
Backhand api layer
Database layer

For creating the first hibernate application, we must know the elements of Hibernate architecture. They are as follows:
SessionFactory
The SessionFactory is a factory of session and client of ConnectionProvider. It holds second level cache (optional) of data. The org.hibernate.SessionFactory interface provides factory method to get the object of Session.

Session
The session object provides an interface between the application and data stored in the database. It is a short-lived object and wraps the JDBC connection. It is factory of Transaction, Query and Criteria. It holds a first-level cache (mandatory) of data. The org.hibernate.Session interface provides methods to insert, update and delete the object. It also provides factory methods for Transaction, Query and Criteria.

Transaction
The transaction object specifies the atomic unit of work. It is optional. The org.hibernate.Transaction interface provides methods for transaction management.

ConnectionProvider
It is a factory of JDBC connections. It abstracts the application from DriverManager or DataSource. It is optional.

TransactionFactory
It is a factory of Transaction. It is optional.

--------------------------------------------------------------

Second-level caching in Hibernate is a powerful feature that helps improve application performance by reducing the number of database queries. Here's a breakdown of what it is and how it works:

---

### 🧠 **What is Second-Level Cache in Hibernate?**

- **First-Level Cache**: Enabled by default, it stores entities within the scope of a Hibernate `Session`. Once the session is closed, the cache is gone.
- **Second-Level Cache**: Optional and configurable, it stores entities across sessions. This means data can be reused between different sessions, reducing database access.

---

### ⚙️ **How Second-Level Cache Works**

- Hibernate interacts with a **cache provider** (e.g., Ehcache, Infinispan, Redis).
- When an entity is requested:
  1. Hibernate checks the first-level cache.
  2. If not found, it checks the second-level cache.
  3. If still not found, it queries the database and stores the result in both caches.

---

### 🛠️ **How to Enable Second-Level Cache**

1. **Add Cache Provider Dependency**  
   Example for Ehcache:
   ```xml
   <dependency>
       <groupId>org.hibernate</groupId>
       <artifactId>hibernate-ehcache</artifactId>
       <version>5.x.x</version>
   </dependency>
   ```

2. **Configure Hibernate Properties**
   ```properties
   hibernate.cache.use_second_level_cache=true
   hibernate.cache.region.factory_class=org.hibernate.cache.ehcache.EhCacheRegionFactory
   ```

3. **Annotate Entities**
   ```java
   @Entity
   @Cacheable
   @org.hibernate.annotations.Cache(usage = CacheConcurrencyStrategy.READ_WRITE)
   public class Product {
       @Id
       private Long id;
       private String name;
   }
   ```

4. **Provide Cache Configuration File**  
   For Ehcache, include `ehcache.xml` in your resources.

---

### 📦 **Cache Strategies**

- `READ_ONLY`: Best for immutable entities.
- `NONSTRICT_READ_WRITE`: Allows some staleness.
- `READ_WRITE`: Ensures strong consistency.
- `TRANSACTIONAL`: Used with JTA transactions.

---

### ✅ **Benefits**

- Reduces database load.
- Improves response time.
- Scales better under high traffic.

---

Would you like a working example or help setting this up in a specific project?
