# Hibernate Interview Questions & Answers

## 1) What is Hibernate?

Hibernate is an open-source and lightweight ORM tool that is used to store, manipulate, and retrieve data from the database.

## 2) What is ORM?

ORM is an acronym for **Object/Relational Mapping**. It is a programming strategy to map objects with the data stored in the database. It simplifies data creation, data manipulation, and data access.

---

## 3) Explain Hibernate Architecture

Hibernate architecture comprises many interfaces such as **Configuration**, **SessionFactory**, **Session**, **Transaction**, etc.

### Architecture Layers

The Hibernate architecture is categorized into four layers:

1. **Java Application Layer** - Your application code
2. **Hibernate Framework Layer** - Core Hibernate logic
3. **Backend API Layer** - Database connectivity
4. **Database Layer** - The actual database

### Key Components

#### SessionFactory
The SessionFactory is a factory of session and client of ConnectionProvider. It holds a second-level cache (optional) of data. The `org.hibernate.SessionFactory` interface provides factory methods to get the object of Session.

- **Scope**: Application-wide (singleton)
- **Thread-safe**: Yes
- **Cost**: Expensive to create

#### Session
The Session object provides an interface between the application and data stored in the database. It is a short-lived object and wraps the JDBC connection. It is a factory of Transaction, Query, and Criteria.

- **Scope**: Per request or transaction
- **Thread-safe**: No (should not be shared)
- **Cache**: Holds a first-level cache (mandatory) of data
- **Methods**: Insert, update, and delete operations

#### Transaction
The Transaction object specifies the atomic unit of work. It is optional. The `org.hibernate.Transaction` interface provides methods for transaction management.

#### ConnectionProvider
It is a factory of JDBC connections. It abstracts the application from DriverManager or DataSource. It is optional.

#### TransactionFactory
It is a factory of Transaction. It is optional.

---

## Second-Level Caching in Hibernate

Second-level caching in Hibernate is a powerful feature that helps improve application performance by reducing the number of database queries. Here's a breakdown of what it is and how it works:

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

#### 1. Add Cache Provider Dependency

Example for Ehcache:
```xml
<dependency>
    <groupId>org.hibernate</groupId>
    <artifactId>hibernate-ehcache</artifactId>
    <version>5.x.x</version>
</dependency>
```

#### 2. Configure Hibernate Properties

```properties
hibernate.cache.use_second_level_cache=true
hibernate.cache.region.factory_class=org.hibernate.cache.ehcache.EhCacheRegionFactory
```

#### 3. Annotate Entities

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

#### 4. Provide Cache Configuration File

For Ehcache, include `ehcache.xml` in your resources.

---

### 📦 **Cache Strategies**

| Strategy | Use Case |
|----------|----------|
| `READ_ONLY` | Best for immutable entities |
| `NONSTRICT_READ_WRITE` | Allows some staleness |
| `READ_WRITE` | Ensures strong consistency |
| `TRANSACTIONAL` | Used with JTA transactions |

---

### ✅ **Benefits**

- Reduces database load
- Improves response time
- Scales better under high traffic

---

Would you like a working example or help setting this up in a specific project?