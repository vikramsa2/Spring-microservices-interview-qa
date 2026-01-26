# Spring-microservices-interview-qa
Creating Interview questions and other possible repo questions
what is Spring Boot ?
--------------------
	Its an open source tool that makes it easier to use JAVA based framework to create microservices and webapps 

Advantage of spring boot
------------------------
	you can use it to create a stand alone applications
	there is no need to deploy war files while using spring boot 
	it doesn required xml config 
	embeded tomcat, JETTY and undertow directly 
	spring boot is easier to launch 
	easier customizaiton and management 

----------------------------------------------

### ⚠️ **Drawbacks of Using Spring Boot**

1. **Memory Consumption**
   - Spring Boot applications tend to consume more memory than traditional Java applications due to embedded servers and auto-configuration.

2. **Startup Time**
   - While faster than traditional Spring apps, Spring Boot can still have relatively slow startup times compared to lightweight frameworks like Micronaut or Quarkus.

3. **Lack of Control**
   - Auto-configuration is convenient but can lead to a lack of transparency and control over what’s happening under the hood.

4. **Complex Debugging**
   - Debugging issues related to auto-configuration or dependency injection can be challenging, especially for beginners.

5. **Large JAR Size**
   - The fat JARs created by Spring Boot include all dependencies, which can lead to large file sizes and longer deployment times.

6. **Overhead for Simple Applications**
   - For small or simple applications, Spring Boot might be overkill, introducing unnecessary complexity and overhead.

7. **Version Compatibility**
   - Keeping up with Spring Boot updates and ensuring compatibility with third-party libraries can be a hassle.

8. **Learning Curve**
   - Despite simplifying Spring, Spring Boot still has a steep learning curve for developers new to the Spring ecosystem.

9. **Hidden Magic**
   - The “convention over configuration” approach can obscure what’s actually happening, making it harder to troubleshoot or customize behavior.

10. **Performance Bottlenecks**
    - If not carefully configured, the default settings and dependencies can introduce performance bottlenecks.

---

Would you like a comparison between Spring Boot and other frameworks like Micronaut or Quarkus?

Features of Spring Boot::
-----------------------------

Auto Configuration
Embedded Web Server
Spring Boot Actuator
Spring Data JPA
Spring Security


Spring Bean Scopes:
---------------------------
Singleton - only one instance of the spring bean will be created for the spring container. This is the default spring bean scope
prototype - A new instance will be created every time the bean is requested from the spring container
request - This is same prototype scope, however it's meant to be used for web applications. Instance will be created for each HTTP request
session - A new session will be created for each HTTP session by the container.
global session - This is used to create global session beans for portlet applications.

@Component
@Scope("prototype")
public class MyPrototypeBean {
    // ...
}

PUT 
==========
When a client needs to replace an existing Resource entirely, they can use PUT. When they’re doing a partial update, they can use HTTP PATCH.Like GET,PUT is Idemeptoent


 @RestController
    @RequestMapping("/products")
    public class ProductController {

        @Autowired
        private ProductRepository productRepository;

        @GetMapping
        public List<Product> getAllProducts() {
            return productRepository.findAll();
        }

      }	

Path Param :/person/{email}, {email} -Path Variable

Query Param :/person?name=Vikram&address=Robie, &{Value}

--------------------------------------
explain about spring boot flow
-------------------------------------

This is a model of spring framework and is used to create standalone spring based applications with minimum efforts
Its developed on top of the core spring framework 
There are four layers in spring boot 
presentation layer
business layer
Persistent layer
database layer

Presentation Layer : this handles the http request and translate the JSON parameters to object and authenticates the request and transfer it to the business layer 
Business Layer:  the business layer handles all the business logic and it consists of service, classes and uses services provided by data access layer. This also 
performs authentication and validation 
Persistent Layer: this contains all the storage logic and translates business objects and to database rows
database Layer: in this layer, crud - create, retrieve, update and delete operations are performed 

The client makes the https request (put/get) the request goes to the controller and the controller maps that request and handles it. After that it calls the service logic if required. In the service layer all the business logics performs. It performs the logic on the data that is mapped to JPA with model classes. A JSP is return to the user if no error occurred 

@Autowire::
---------------
@Autowire is an annotation in the Spring Framework that allows Spring to automatically inject dependencies into a component.
It can be applied to fields, setter methods and contructors Injection types.

@Service::
--------------
It is a Spring annotation used to mark a class as a service provider. It indicates that the class contains business logic and then Spring's component scanning to detect and register it as a Spring Bean.

@SpringBootApplication::
---------------------------	

It's a entry point of main class in spring boot application and it holds @SpringBootConfiguration, @enableautoconfiguration, @Componentscan

@SpringBootConfiguration: Indicates that the class is a source of bean definitions. It replaces the need for separate configuration classes and allows bean definitions in the application to be automatically picked up.(only @bean)

@EnableAutoConfiguration: Instructs Spring Boot to automatically configure beans and settings based on the project's dependencies (e.g., setting up the web server if Spring Web is on the classpath).( @Component, @Configuration, @Bean, and meta-annotations for building custom stereotype annotations)

@ComponentScan: Scans for Spring components (like @Controller, @Service, @Repository, etc.) in the package of the main class and its sub-packages.

@Bean::
--------
This is declared at method level and in @configuration classes to indicate that a method produces a bean that is to be managed by the spring IOC container.


Spring Boot CLI ::
----------------------

It's a Command Line Interface, Spring boot software to run and test Spring Boot Application from command prompt.

./spring run className.groovy;


How we will Asynchronize project in spring Boot:
------------------------------------------------
By using @EnableAsync annotation to create Asynchronization project in spring Boot Application.
Inlcude executaor services using COnfiguration File and use it in service

Key components of spring boot
------------------------------
	Spring boot starters, spring boot auto configuration, spring boot CLI, spring boot actuator 

Spring initializr
-----------------
	Its a web based tool using which we can easily generate the structure of the spring boot project.
	It also provides various different features of the projects expressed in the metaData model 
	This model allows us to configure the list of dependencies that are supported by JVM 


IOC - Inversion of control. Its container is the core of spring framework. It creates the objects, configures and 
----	assembles their depencies , manages their entire life cycle. The container uses dependency injection (DJ) to manage the components that make up the 
	application 

@Component is an annotation that allows Spring to detect our custom beans automatically.
The @Controller is a specialization of @Component annotation while @RestController is a specialization of @Controller annotation.
Controllers are responsible for handling incoming web requests, processing them, and returning the appropriate response

diff bwn @controller and @rest controller
-----------------------------------------
	@Controller							@RestController
It is used to mark classes as SPring MVC COntroller 		Its a special controller used in restful webservices and its 
									the combination of @Controller and @ResponseBody
Its a specialized version of @Component 			Its specialized version of @Controller
we can return a view in spring web MVC 				We cannot return a view
we need to use @ResponseBody on every handler method		We dont need to use @ResponseBody on every handler method

whats spring boot acturator 
---------------------------
	Spring boot acturator Endpoints let us monitor and interact with our application
	Its a spring boot sub module and provides build in endpoints that we can enable and disable for our application 

How to enable actuator in spring boot application
----------------------------------------------
Add actuator dependency
enable endpoints in applicaiton.properties 
Run your spring boot app 
Now we can access actuator endpoints URI on the management portal 


@Repository
-----------
Its used to indicate that the class provides the mechanism for storage, retrival, search, update and delete operation on objects 

starter dependency of spring boot
--------------------------------
Spring-boot-starter-web
Spring-boot-starter-web-services 
Spring-boot-starter-integration
Spring-boot-starter-jdbc
Spring-boot-starter-validation
Spring-boot-starter-test
Spring-boot-starter-security 


diff bwn spring and spring boot 
------------------------------------
		Spring									Spring Boot
Its widely used Java EE framework for building applications		Its widely used to develop REST API 
It makes developer more productivity 					SHorten the code lengt and provide the easiest way to develop web app
Primary feature of the spring framework is dependency injection		Primary feature of the spring framework is auto configuration 
It helps to make things simpler by allowing us to develop		It helps to create standalone app with less configuration 	
loosley coupled apps 					
Developer writer a lot of code to do minor task 			It reduce the boiler plate code 
It doesn't provide for an in-memory db					It offer several plugins for working with an embedded and in-memory db
developer manualy defines dependencies for spring project in 		Spring boot comes with concept of starter in pom.xml file that internally takes
pom.xml									care of downloading the dependencies jar files 

diff bwn spring boot and spring MVC
--------------------------------------
		Spring Boot								Spring MVC
It provides default config to build spring powered framework		It provides ready to use features for building a web app 
THere is no need to build config manually				It requires build config manually
There is no requirement for a deployment descriptor			Deployment descriptor is required 
It avoid boiler plate code and wraps dependencies together		Its specifieds each dependency seperately 
	in a single unit					
It reduce development time and increase productivity			It makes more time to achieve the same

diff bwn requestMapping and getMapping
--------------------------------------
		RequestMapping								GetMapping
Its purpose to handle various types of http request 		Purpose is to specifically handles http getrequest 
get, post etc
@RequestMapping								@GetMapping
@RequestMapping(value="/example",method=RequestMethod.GET)	@GetMapping("/example")


@SpringBootApplication and @EnableAutoConfiguration diff
--------------------------------------------------------
		@SpringBootApplication							@EnableAUtoConfiguration
This is auto configuration						This is customized auto configuration 
It is the entry point used on the main class of a sprint boot		Can be used on any config class in conjuction with @SpringBootApplication
application 
Includes @ComponentsScanning to enable components scanning		Doesn't perform components scanning by itself 	

Purpose of @ComponentsScan in class file
----------------------------------------
It is used to tell spring to scan package and automatically detects spring components, configuration and services to configure 
The @ComponentsScan can be used in the following ways 
without argument
with basepackage classess
with base packages 

@SpringBootApplication internal works
-------------------------------------
For the server port, the property we want to change is server.port

How you will change the server portal in spring boot project
------------------------------------------------------------
By default, the embddede server starts on port 8080 
we can do the same is we are using an application.yml file: 
server:
  port: 8081

how to set the property in the main @SpringBootApplication class

	@SpringBootApplication
	public class CustomApplication {
		public static void main(String[] args){
	SpringApplication app = new SpringApplication(CustomApplication.class);
	app.setDefaultProperties(Collections.singleMap("server.port","8083"));
		app.run(args);
	}
}

To customize the server configuration, we have to implement the 
WebServerFactoryCustomizer interface:
	@component
	public class ServerPortCustomizer implements WebServerFactoryCustomizer<ConfigurableWebServerFactory> {
		@Override
		public void customize(ConfigurableWebServerFactory factory){
			factory.setPort(8086	);
		}
	{


how you will change the server in spring boot application 
-----------------------------------------------------------
configurations {
	//exclude Reactor Netty
	compile.exclude module: 'spring-boot-starter-tomcat'
  }
dependencies {
	compile 'org.springframework.boot:spring-boot-starter-undertow'
}

we need to exclude the tomcat server in the configuration and add the new server in dependency injection 

how did you disable the default web server
-------------------------------------------
disable the default web server if we configure spring.main.web-application-type = none in application.property file 


securing spring boot with spring security 
------------------------------------------
for the security purpose we configured the dependency "spring-boot-starter-security" in application.property 

RequestMapping and RestController
----------------------------------
Request Mapping is used to map http request to handle methods in your controller classess
It can be used at the class level and method level  
http method -  get, post, put and delete
URL Path 
URL parameters 
Request Headers

Rest controller
Its a convenient annotation that combines @controller and @responsebody annotation 
It indicates a controller where every method returns a domain object instead of a view 


what is dependency injection and its types?
-------------------------------------------
It is a design pattern that enables us to produce loosely coupled components 
In dependency injection an object ability to complete a task dependency on another object 
THree types of dependency
constructorInjection - its most common type of DI in springboot. Here, the dependency object is injected into the dependent object constructor 
SetterInjection - the dependency object is injected into dependent object setter method 
FieldInjection - the dependency object is injected into the dependent object field 


When bean will be create in Spring Boot Project:
-------------------------------------------------
In a Spring Boot project, beans are created when the Spring container starts up and initializes the application context,
either through component scanning, explicit configuration, or auto-configuration. 
Specifically, beans are created and initialized in the following scenarios:

1.Component Scanning:
When we annotate a class with @Component, @Service, @Repository or @Controller. Spring's component scanning automatically detects these classes,
and they are instantiated as beans in the application context.
2.Configuration Classes:
If a class is annotated with @Configuration, any method within it that is annotated with @Bean will be executed, and the returned object will be 
registered as a bean in the application context.
3.Auto-Configuration:
Spring Boot's auto-configuration mechanism can automatically create beans based on the classpath and existing beans.
This happens when you annotate your main application class with @SpringBootApplication
4.Bean Factory or context Initialization:
Beans are also created when the ApplicationContext is initialized. The Spring container creates the necessary beans and manages their lifecycle.
5.Explicitly Defined Beans:
Beans can be explicitly defined using XML configuration or Java Based configuration (@Bean method)

Beans are typically created,
Singleton Beans: Created during the startup of the application context.
Prototype Beans: Created each time they are requested from the container (@Scope(ConfigurableBeanFactory.SCOPE_PROTOTYPE))
Lazy Beans: created only when they are first needed, not at startup. This can be configured using @Lazy. 


Environment Configuration in Spring Boot Project:
---------------------------------------------------
Spring Boot provides a robust and flexible way to manage environment configurations through properties files, profiles, and externalized configurations.
This allows you to easily switch between different configurations depending on the environment in which the application is running.

1.Application Properties/YAML Files:
Spring Boot allows you to define environment-specific properties in application.properties or application.yml
application.dev.properties/application.dev.yml, application.test.properties,application.test.yml...
To active profile determines which file is loaded. For example spring.profiles.active = dev
2.Profiles:
Profiles in Spring Boot allow you to define different beans and configurations for different environments.
You can use the @Profile annotation to specify that a bean should only be loaded in a particular environment. ex, 
@Configuration 
@Profile("Dev")
public class DevConfiguration{
  @Bean
  public DataSource datasource(){
}}	
3.Environment Specific Beans:
Using @Profile, you can conditionally load beans based on the active environment.
@Bean
@Profile("Prod")
public MyService myServiceProd(){
 return new MyServiceImplForProd();
}
4.Configuration Environment Variables:
You can also configure environment variables that can be used in your application. These variables can be injected using @Value.
#application.properties
myapp.datasource.username = ${DB_USERNAME}

@Value("${myapp.datasource.username}")
private String dbUserName;

 


Spring Boot Security 
-----------------------
1.Primary security framework for securing Spring applications 
spring-boot-starter-security

2. Configuration security settings
Create a security configuration class by extending "WebSecurityConfigurerAdapter" and override methods to customize security settings,@EnableWebSecurity


3. Password encoding
Use PasswordEncoder to encode the passwords

4. Method level security
Enable method-level security with @EnableGlobalMethodSecurity and use @preAuthorize annotation

@Configuration
    @EnableMethodSecurity(prePostEnabled = true)
    public class SecurityConfig {
    }


 @GetMapping("/user")
        @PreAuthorize("hasAnyRole('ADMIN', 'USER')")
        public String userEndpoint() {
            return "User access granted";
        }



5. Secure API with OAuth2
Use OAuth2 for securing REST APIs. 
Spring-boot-starter-oauth2-resource-server

6.HTTPS/SSL (Secure Socket Layer)
Configure your application to use HTTPS by proving SSL configuration in application.properties 
server.port = 8443
server.ssl.key-store = classpath:keystore.p12
server.ssl.key-store-password=
server.ssl.keystoreType=PKCS12
server.ssl.keyAlias = tomcat


Vulnerabilities in a Spring Boot Project
------------------------------------------

1. Cross-Site Request Forgery
Ensure CSRF protection is enabled.
http.csrf().csrfTokenRepository(CookieCsrfTokenRepository.WithHttpOnlyFalse());
2. Avoid Java serialization; use JSON or XML with Strict Schemas. Validate data before deserializing
ObjectMapper Class 
3. Disable unnecessary features and ensure secure defaults
4. SQL Injection - use parameterized queries, prevent direct execution of user input
5. Encrypt sensitive data in transit, Use strong encrytion algorithms
Configure your application to use HTTPS by proving SSL configuration in application.properties 
server.port = 8443
server.ssl.key-store = classpath:keystore.p12
server.ssl.key-store-password=
server.ssl.keystoreType=PKCS12
server.ssl.keyAlias = tomcat
6. Use strong authentication methods, secure session cookies and implement session timeouts
configure(HttpSecurity http) {http.sessionManagement().sessionCreationPolicy(SessionCreationPolicy.IF_REQUIRED).invalidSessionUrl().maximumSessions(1).expiredUrl();}


SQL Injection
SQL injection is a code injection technique that might destroy your database.
SQL injection is one of the most common web hacking techniques.
SQL injection is the placement of malicious code in SQL statements, via web page input.

uName = getRequestString("username");
uPass = getRequestString("userpassword");
sql = 'SELECT * FROM Users WHERE Name ="' + uName + '" AND Pass ="' + uPass + '"'


 Parameterized Queries
This technique consists of using prepared statements with the question mark placeholder (“?”) in our queries whenever we need to insert a user-supplied value.
Java JDBC
PreparedStatement p = c.prepareStatement(sql);
    p.setString(1, customerId);
    ResultSet rs = p.executeQuery(sql)); 

JPA
String jql = "from Account where customerId = :customerId";
TypedQuery<Account> q = em.createQuery(jql, Account.class)
  .setParameter("customerId", customerId);


Service Versioning:
---------------------
Service versioning in Spring Boot is crucial when you need to evolve your API's while ensuring that existing clients continue to work without interruption.

1.URI Versioning: The version is included as part of the URL path
@RestController
@RequestMapping("/api/V1/products")

2.Request Parameter Versioning: The version is specified as a query parameter in the request URL.
@RestController
@RequestMapping("/api/products")
public class ProductController{
@GetMapping(params = "Version=1")

3.Header Versioning: The version is specified in the request headers
@RestController
@RequestMapping("/api/products")
public class ProductController{
@GetMapping
public List<Product> getAllProducts(@RequestHeader("X-API-version") String apiVersion){
if("1".equals(apiVersion)){ getAllProductsV1(); }


How you will redirect from one service to another:
-----------------------------------------------------

By using HTTPStatus code we will redirect to another service
Status code : 301 - Moved Permanently 302 - Temporary Redirect, 
307 - Temporary Redirect (Method and body will not be changed during the redirection)
308 - Permanent Redirect (Method and body will not be changed during the redirection)


400 - Bad request
401 - Unauthorized
200 - OK 
201 - Created
500 - Internal Server error

Put and Patch:
---------------
Put - Will update entire resource 
Patch - It will update partially resource


HTTP Method :
-----------------
GET : Retrieve a resource or a collection of resource
POST : Create a new resource
PUT : Update an existing resource entirely
PATCH : Update a resource partially
DELETE : Delete a resource


Experiencing a performance issues, request taking too long to process, how to identify and resolve it:
--------------------------------------------------------------------------------------------------------
we can use Profiling tools(like Spring Boot Actuator, Micrometer) Optimizing database queries, handling caching strategies(ex, Redis, Ehcache) and Asynchronous processing
	

How would you prevent your service from failing when the third-party service is down?
--------------------------------------------------------------------------------------
we can use Resilience4j, Circuit breaker patterns, fallback methods and timeouts.


Deploying a Spring Boot application that requires a graceful shutdown to complete ongoing requests before shutting down. How would you implement this?
-------------------------------------------------------------------------------------------------------------------------------------------------------
Spring Boot Actuator, Shutdown hooks, @preDestroy annotation


In Spring Boot application where multiple users can trigger the same business operation concurrently. How would you ensure data consistency and avoid race conditions:
----------------------------------------------------------------------------------------------------------------------------------------------------------------------
@Synchronized, @Lock, @Transactional


what is data JPA/Spring boot jpa ?
-----------------
its a java specification for managing relational data in java application 
it allows us to access and persists data bwn java object class and relational database 
JPA follows object relational mapping (ORM)


diff bwn java JPA and hibernate?
----------------------------------
			JPA							hibernate
Java persistence API - defines the management of relational		This is an object relational mapping (ORM) tool which is used to save the state of 
data in the java application 							java object into database

Its just a specification various ORM tool implement it for data		It is one of the most frequently used JPA implementation 
persistance 

its coming under javaX.persistance					Comes under org.hibernate
uses java persistance query language as an object oriented query 	It uses hibernate query language (HQL) as an object oriented query
language to perform db operations (JPQL)					language to perform db operations

Uses entity manager, interface to create read and delete		Use a session interface to create read and update delete operations 
operations for instance of mapping entity classes				for the instance of mapping entity classes

The entity manager factory interface is used to interact with the 	It use a session factory interface to create session instances 		
entity manager factory for the persistant unit. Thus it provides an 
entity manager
---------------------------------------------------------------------------------------------------
Exception handling in Spring boot

@ControllerAdvice annotation allows us to consolidate our multiple, scattered @ExceptionHandlers from before into a single, global error handling component.

@ControllerAdvice
public class RestResponseEntityExceptionHandler 
  extends ResponseEntityExceptionHandler {

    @ExceptionHandler(value 
      = { IllegalArgumentException.class, IllegalStateException.class })
    protected ResponseEntity<Object> handleConflict(
      RuntimeException ex, WebRequest request) {
        String bodyOfResponse = "This should be application specific";
        return handleExceptionInternal(ex, bodyOfResponse, 
          new HttpHeaders(), HttpStatus.CONFLICT, request);
    }
}

------------------------------------------------------------------------------------------------------
How to configure Authentication in Spring Security?
To configure Authentication in Spring Security (not basic authentication) we need to follow below procedure:

Extend WebSecurityConfigureAdapter in a custom class and use @EnableWebSecurity annotation.
Overrides configure(AuthenticationManagerBuilder) method.
Configure type of auth, user, password and role.
Now, this will automatically create and configure a new Authentication Manager and then Spring Security will use this Authentication Manager instead of using the default one.
----------------------------------------------------------------------------------------------------------

spring-boot-actuators
For example, we can create a health group named custom by adding this to our application.properties:

management.endpoint.health.group.custom.include=diskSpace,ping
It’s also possible to show these details only for authorized users:

management.endpoint.health.group.custom.show-components=when_authorized
management.endpoint.health.group.custom.show-details=when_authorized



Now, if we call the /actuator/health endpoint, it will tell us about the new health group in the JSON response:

{"status":"UP","groups":["custom"]}

With health groups, we can see the aggregated results of a few health indicators.

In this case, if we send a request to /actuator/health/custom:

{"status":"UP"}

Then, we can configure the group to show more details via application.properties:

management.endpoint.health.group.custom.show-components=always
management.endpoint.health.group.custom.show-details=always

Now, if we send the same request to /actuator/health/custom, we’ll see more details:

{
  "status": "UP",
  "components": {
    "diskSpace": {
      "status": "UP",
      "details": {
        "total": 499963170816,
        "free": 91300069376,
        "threshold": 10485760
      }
    },
    "ping": {
      "status": "UP"
    }
  }
}


-----------------------------------------------------------------------------------

what is a circuit breaker 
Consider the following scenario: Service A invokes Service B, but unfortunately, Service B is either unavailable or unable to respond. Consequently, Service A might wait for responses from Service B or handle the exceptions encountered. Subsequent requests directed at Service B will encounter similar challenges, leading to a bad user experience. In such cases, circuit breaker can help by stopping request sending for a specific time, waiting for the timeout ends, enable a limited number of requests to check whether Serice B is working. If those requests succeed, it allows microservices to continue normal operations. If not, it will again start the timeout.


Circuit Breaker has three states: Closed, Open, and Half_Open.

1. Closed
Closed is the initial state of circuit breaker. When microservices run and interact smoothly, circuit breaker is Closed. It keeps continuously monitoring the number of failures occurring within the configured time period. If the failure rate exceeds the specified threshold, Its state will change to Open state. If not, it will reset the failure count and timeout period.

2. Open
During Open state, circuit breaker will block the interacting flow between microservices. Request callings will fail, and exceptions will be thrown. Open state remains until the timeout ends, then change to Half_Open state.

Fallback Mechanism:
When the circuit breaker is in the open state, instead of allowing requests to reach the failing external API, it redirects them to a fallback method or a pre-defined response. In the context of our example, the fallback method could be retrieving a cached version of the country list or providing a default list.

3. Half_Open
In Half_Open state, circuit breaker will allow a limited of number requests to pass through. If the failure rate is greater than the specified threshold, it switches again to Open state. Otherwise, it is Closed state.

-----------------------------------------------------------------------------------

Redis Config 

# application.properties
spring.redis.host=localhost
spring.redis.port=6379
spring.cache.type=redis

Enable Caching in Spring Boot : Use @EnableCaching in Main class of Spring boot

@SpringBootApplication
@EnableCaching
public class RedisCacheApplication {
    public static void main(String[] args) {
        SpringApplication.run(RedisCacheApplication.class, args);
    }
}


Implement Caching: simply use the @Cacheable annotation

@Service
public class UserService {

    @Cacheable(value = "userCache", key = "#userId")
    public User getUserById(Long userId) {
        // Simulate a database call
        return userRepository.findById(userId).orElseThrow(() -> new UserNotFoundException());
    }
}

@Cacheable: Caches the method's return value using the given cache name (userCache in this case).
key: Specifies the key under which the value will be stored. By default, all method arguments are considered part of the key.

@CachePut: Updates the values in the cache with a new value.
@CacheEvict: eliminates a record from the cache.

@Service
public class UserService {

    @CacheEvict(value = "userCache", key = "#userId")
    public void deleteUserById(Long userId) {
        userRepository.deleteById(userId);
    }

    @CachePut(value = "userCache", key = "#user.id")
    public User updateUser(User user) {
        return userRepository.save(user);
    }
}

Customizing Cache Expiration

Redis lets you specify the time-to-live (TTL) for entries that are cached. You can set the TTL in your cache manager using Spring Boot.

@Configuration
public class RedisCacheConfig {

    @Bean
    public RedisCacheConfiguration cacheConfiguration() {
        return RedisCacheConfiguration.defaultCacheConfig()
                .entryTtl(Duration.ofMinutes(10)) // Set TTL to 10 minutes
                .disableCachingNullValues();
    }
}

----------------------------------------------------------------------------------------

Pagination in Spring boot /JPA which repo class to use -
extending from PagingAndSortingRepository
Pageable sortedByPriceDescNameAsc = 
  PageRequest.of(0, 5, Sort.by("price").descending().and(Sort.by("name")));
---------------------------------------------------------------------------------------------

What is security used in API ,Spring security JWT Implemenattaion -JWT , 2FA - Done

Implementing JWT (JSON Web Token) in a Spring Boot application typically involves integrating it with Spring Security to handle authentication and authorization. The general steps are as follows:
Project Setup and Dependencies:
Create a new Spring Boot project using Spring Initializr.
Add necessary dependencies to your pom.xml (for Maven) or build.gradle (for Gradle). Key dependencies include spring-boot-starter-security, spring-boot-starter-web, and a JWT library like jjwt (Java JWT).

Code :
@Service
public class JwtService {
    @Value("${security.jwt.secret-key}")
    private String secretKey;

    @Value("${security.jwt.expiration-time}")
    private long jwtExpiration;

    public String extractUsername(String token) {
        return extractClaim(token, Claims::getSubject);
    }

    public <T> T extractClaim(String token, Function<Claims, T> claimsResolver) {
        final Claims claims = extractAllClaims(token);
        return claimsResolver.apply(claims);
    }

    public String generateToken(UserDetails userDetails) {
        return generateToken(new HashMap<>(), userDetails);
    }

    public String generateToken(Map<String, Object> extraClaims, UserDetails userDetails) {
        return buildToken(extraClaims, userDetails, jwtExpiration);
    }

    public long getExpirationTime() {
        return jwtExpiration;
    }

    private String buildToken(
            Map<String, Object> extraClaims,
            UserDetails userDetails,
            long expiration
    ) {
        return Jwts
                .builder()
                .setClaims(extraClaims)
                .setSubject(userDetails.getUsername())
                .setIssuedAt(new Date(System.currentTimeMillis()))
                .setExpiration(new Date(System.currentTimeMillis() + expiration))
                .signWith(getSignInKey(), SignatureAlgorithm.HS256)
                .compact();
    }

    public boolean isTokenValid(String token, UserDetails userDetails) {
        final String username = extractUsername(token);
        return (username.equals(userDetails.getUsername())) && !isTokenExpired(token);
    }

    private boolean isTokenExpired(String token) {
        return extractExpiration(token).before(new Date());
    }

    private Date extractExpiration(String token) {
        return extractClaim(token, Claims::getExpiration);
    }

    private Claims extractAllClaims(String token) {
        return Jwts
                .parserBuilder()
                .setSigningKey(getSignInKey())
                .build()
                .parseClaimsJws(token)
                .getBody();
    }

    private Key getSignInKey() {
        byte[] keyBytes = Decoders.BASE64.decode(secretKey);
        return Keys.hmacShaKeyFor(keyBytes);
    }
}
---------------------------------------------------------------------------------------------

What is Throttling?
Throttling is the process of limiting the rate that an API is being used in a server. It limits the number of service requests which can be executed in a unit time (for a second, minute..).

Rate limiting is a strategy to limit access to APIs. It restricts the number of API calls that a client can make within a certain time frame. This helps defend the API against overuse, both unintentional and malicious.

Rate limits are often applied to an API by tracking the IP address, or in a more business-specific way, such as API keys or access tokens. As API developers, we have several options when a client reaches the limit:

Queueing the request until the remaining time period has elapsed
Allowing the request immediately, but charging extra for this request
Rejecting the request (HTTP 429 Too Many Requests)
3. Bucket4j Rate Limiting Library

3.1. What Is Bucket4j?
Bucket4j is a Java rate-limiting library based on the token-bucket algorithm. Bucket4j is a thread-safe library that can be used in either a standalone JVM application, or a clustered environment. It also supports in-memory or distributed caching via the JCache (JSR107) specification.


import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;


public class RateLimitingService {

    private final Map<String, Bucket> buckets = new ConcurrentHashMap<>();

    public boolean allowRequest(String apiKey) {
        Bucket bucket = buckets.computeIfAbsent(apiKey, this::createNewBucket);
        return bucket.tryConsume(1);
    }

    private Bucket createNewBucket(String apiKey) {
        Bandwidth limit = Bandwidth.classic(10, Refill.intervally(10, Duration.ofMinutes(1)));
        return Bucket4j.builder().addLimit(limit).build();
    }
}

-=========================================================================================

Introduction to OAuth2:

OAuth2 is an authorization framework that allows applications to obtain limited access to user accounts on an HTTP service.
It works by delegating user authentication to the service that hosts the user account and authorizing third-party applications to access the user account.

OAuth2 Roles:
Resource Owner: The user who authorizes an application to access their account.
Client: The application requesting access to the user's account.
Resource Server: The server hosting the protected resources.
Authorization Server: The server that authenticates the user and issues access tokens.

OAuth2 Grant Types:
Authorization Code Grant: Used for server-side applications.
Implicit Grant: Used for client-side applications.
Resource Owner Password Credentials Grant: Used when the user trusts the client.
Client Credentials Grant: Used for machine-to-machine communication.

Implementing OAuth2 in Spring Boot:

To configure OAuth2 in a Spring Boot application using spring-boot-starter-oauth2-client and spring-boot-starter-security.
Discuss the use of application.yml or application.properties to configure client credentials, authorization server details, and scopes.
Code Example:

Briefly describe a simple example of configuring OAuth2 in a Spring Boot application:

@Configuration
public class SecurityConfig extends WebSecurityConfigurerAdapter {
    @Override		
    protected void configure(HttpSecurity http) throws Exception {
        http
            .authorizeRequests()
            .antMatchers("/login").permitAll()
            .anyRequest().authenticated()
            .and()
            .oauth2Login();
    }
}
Explain that this configuration sets up OAuth2 login and secures all endpoints except the login page.
Common Use Cases:

Discuss common scenarios where OAuth2 is used, such as securing REST APIs, single sign-on (SSO), and integrating with third-party services like Google, Facebook, or GitHub.
Security Considerations:

Highlight the importance of securing access tokens, using HTTPS, and following best practices to prevent security vulnerabilities.

=======================================================================================

Spring JPA Annotations Guide
This lesson covered the most notable Spring Data JPA annotations used to define database tables from within Java objects. They are:

@Entity - marks a class as persistable
@Table - can be used to specify table names and the schema where the table should be located
@Id - indicates the field shall act as the ID/primary key column for the table
@GeneratedValue - used in conjunction with @Id to have Spring generate the primary key for you
@Column - allows control over column settings such as name and length
@Transient - indicates that the field is not to be persisted in the database and should be ignored by JPA
@Document - for Mongodb
@Embeddable & EmbeddableId - For Composite PK

@Transactional
@Query("SELECT COUNT(*) FROM Person p",native=true)

@NamedStoredProcedureQueries({ 
    @NamedStoredProcedureQuery(
        name = "count_by_name", 
        procedureName = "person.count_by_name", 
        parameters = { 
            @StoredProcedureParameter(
                mode = ParameterMode.IN, 
                name = "name", 
                type = String.class),
            @StoredProcedureParameter(
                mode = ParameterMode.OUT, 
                name = "count", 
                type = Long.class) 
            }
    ) 
})

@Param
@Query("FROM Person p WHERE p.name = :name")
Person findByName(@Param("name") String name);

@EnableJpaRepositories

-----------------------------------------------------------------------------------
Interceptor

To work with interceptor, you need to create @Component class that supports it and 
*** it should implement the HandlerInterceptor interface.

The following are the three methods you should know about while working on Interceptors:

1.preHandle() method: This is used to perform operations before sending the
request to the controller. This method should return true to return the response to
the client.
2. postHandle() method: This is used to perform operations before sending the
response to the client.
3. afterCompletion() method: This is used to perform operations after completing
the request and response.

Custom Logger Interceptor
In this example, we’ll focus on logging in our web application.

First, our class needs to implement HandlerInterceptor:

public class LoggerInterceptor implements HandlerInterceptor {
    ...
}
----------------------------------------------------------------------------------
Cross-Origin Resource Sharing (CORS)

Cross-Origin Resource Sharing (CORS) is a security concept that allows restricting the
resources implemented in web browsers. It prevents the JavaScript code producing or
consuming the requests against different origin.
For example, your web application is running on 8080 port and by using JavaScript you
are trying to consuming RESTful web services from 9090 port. Under such situations, you
will face the Cross-Origin Resource Sharing security issue on your web browsers

@CrossOrigin annotation for the controller method. This @CrossOrigin annotation supports specific REST API, and not for the entire application.

@RequestMapping(value = "/products")
@CrossOrigin(origins = "http://localhost:8080")
public ResponseEntity<Object> getProduct() {
return null;
}


Global CORS Configuration
We need to define the shown @Bean configuration to set the CORS configuration support globally to your Spring Boot application.
   
 @Configuration
    public class WebConfig implements WebMvcConfigurer {
        @Override
        public void addCorsMappings(CorsRegistry registry) {
            registry.addMapping("/**") // Apply to all paths
                    .allowedOrigins("http://localhost:4200")
                    .allowedMethods("GET", "POST", "PUT", "DELETE")
                    .allowedHeaders("*");
        }
    }
--------------------------------------------------------------------------------------------

WebSecurityConfigurerAdapter allowed developers to customize Spring Security's web security features by extending the class and overriding methods like configure(HttpSecurity http). 
allows customization to both WebSecurity and HttpSecurity


What it handled:
Authentication: Verifying user identity (e.g., username/password, JWT, OAuth). 
Authorization: Controlling access to resources based on roles and permissions. 
CSRF Protection: Preventing cross-site request forgery attacks. 
Session Management: Handling user sessions securely. 
========================================================================================

Spring Security offers several additional configurations to enhance your application’s security:

Enable HTTPS by configuring an SSL certificate.
Configure CORS and CSRF protection for cross-origin requests.
Limit the number of login attempts to prevent brute force attacks.
Implement proper password hashing and storage using strong password encoders like BCryptPasswordEncoder.
Utilize Content Security Policy (CSP) headers to mitigate cross-site scripting (XSS) and other code injection attacks.
Configure session timeouts and automatic session invalidation after a specified period of inactivity.
========================================================================================

 
 With the deprecation of WebSecurityConfigurerAdapter, the new recommended approach is to define security using SecurityFilterChain as a bean.

dlKey Changes
No Extending Class: Instead of extending a class, we now declare a bean (SecurityFilterChain) to configure security.
HttpSecurity Lambda Syntax: We use method references (authorizeHttpRequests, formLogin, etc.) and lambda expressions to make the configuration more declarative and modular.
Bean-Based Configuration: Everything is done using beans, which is more in line with modern Spring practices.

@Configuration
@EnableWebSecurity
public class SecurityConfig {

    @Bean
    SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
        http
            .authorizeHttpRequests(auth -> auth
                .requestMatchers("/admin/**").hasRole("ADMIN")
                .requestMatchers("/user/**").hasRole("USER")
                .requestMatchers("/").permitAll())
            .formLogin(login -> login
                .loginPage("/login")
                .permitAll())
            .logout(logout -> logout
                .permitAll());
        return http.build();
    }
}

========================================================================================

Creating a Spring Boot service involves several steps. Here's a concise guide to get you started:

1. **Set Up Your Development Environment**:
   - Install Java Development Kit (JDK).
   - Install an Integrated Development Environment (IDE) like IntelliJ IDEA or Eclipse.
   - Install Maven or Gradle for dependency management.

2. **Create a New Spring Boot Project**:
   - Use Spring Initializr (https://start.spring.io/) to generate a new Spring Boot project.
   - Select project metadata (e.g., Maven/Gradle, Java version, dependencies like Spring Web, Spring Data JPA).

3. **Import the Project into Your IDE**:
   - Open your IDE and import the generated project.

4. **Create a Controller**:
   - Create a new Java class annotated with `@RestController`.
   - Define request mappings using `@RequestMapping` or `@GetMapping`, `@PostMapping`, etc.

   ```java
   @RestController
   public class MyController {
       @GetMapping("/hello")
       public String hello() {
           return "Hello, World!";
       }
@PostMapping(value = "/processXml", consumes = MediaType.APPLICATION_XML_VALUE)
public ResponseEntity<String> processXmlData(@RequestBody MyXmlData xmlData) {
    // Process the received XML data
    return ResponseEntity.ok("XML data received and processed successfully");
}
   }
   ```

5. **Create a Service Layer**:
   - Create a service class annotated with `@Service`.
   - Implement business logic in this class.

   ```java
   @Service
   public class MyService {
       public String getGreeting() {
           return "Hello from Service!";
       }
   }
   ```

6. **Integrate Service with Controller**:
   - Autowire the service into the controller.

   ```java
   @RestController
   public class MyController {
       @Autowired
       private MyService myService;

       @GetMapping("/greet")
       public String greet() {
           return myService.getGreeting();
       }
   }
   ```

7. **Run Your Application**:
   - Use the main class annotated with `@SpringBootApplication` to run your application.

   ```java
   @SpringBootApplication
   public class MyApplication {
       public static void main(String[] args) {
           SpringApplication.run(MyApplication.class, args);
       }
   }
   ```

8. **Test Your Endpoints**:
   - Use tools like Postman or curl to test your endpoints.

--------------------------------------------------------------------

https://medium.com/@tericcabrel/implement-jwt-authentication-in-a-spring-boot-3-application-5839e4fd8fac



Transaction management in Spring Boot ensures data integrity by treating a sequence of operations as a single unit. If any operation fails, the entire transaction is rolled back, preventing inconsistencies. Here's how to maintain transactions:

1. Declarative Transaction Management with @Transactional:

Annotation:
The @Transactional annotation is the primary way to manage transactions in Spring Boot. It can be applied at the class or method level.

Functionality:
When a method annotated with @Transactional is called, Spring automatically starts a transaction before the method execution and commits the transaction if the method completes successfully. If an exception occurs, the transaction is rolled back.
Auto-Configuration:
If you use spring-boot-starter-data-jpa, Spring Boot auto-configures transaction management. Otherwise, you can enable it by adding @EnableTransactionManagement to your main application class.

    import org.springframework.transaction.annotation.Transactional;
    import org.springframework.stereotype.Service;

    @Service
    public class MyService {

        @Transactional
        public void performTransaction() {
            // Database operations here
        }
    }


2. Programmatic Transaction Management:
PlatformTransactionManager:
This interface defines the basic operations for transaction management. You can directly manage transactions using PlatformTransactionManager.

Transaction Definition:
You can create a TransactionDefinition object to specify transaction properties.

Manual Control:
You can start, commit, or rollback transactions manually using the getTransaction, commit, and rollback methods of PlatformTransactionManager.

    import org.springframework.transaction.PlatformTransactionManager;
    import org.springframework.transaction.TransactionDefinition;
    import org.springframework.transaction.TransactionStatus;
    import org.springframework.transaction.support.DefaultTransactionDefinition;
    import org.springframework.beans.factory.annotation.Autowired;
    import org.springframework.stereotype.Service;

    @Service
    public class MyService {
        @Autowired
        private PlatformTransactionManager transactionManager;

        public void performTransaction() {
            TransactionDefinition def = new DefaultTransactionDefinition();
            TransactionStatus status = transactionManager.getTransaction(def);
            try {
                // Database operations here
                transactionManager.commit(status);
            } catch (Exception e) {
                transactionManager.rollback(status);
            }
        }
    }

Distributed Transactions:
Two-Phase Commit (2PC): A protocol that ensures that all participants in a distributed transaction either commit or roll back.
Saga Pattern: A sequence of local transactions, each updating data within a single service, which is suitable for microservices architecture.
Transactional Outbox Pattern: Ensures that data changes and events are published atomically.


---------------------------------------------------------------------------------

centralized configuration management spring boot

Centralized configuration management in Spring Boot involves managing application configurations from a single, central location. This approach offers several benefits, including simplified management, consistency across environments, and the ability to update configurations without restarting applications.

Key Components
Spring Cloud Config Server:
This server acts as the central repository for all configuration data. It supports various backends, such as Git repositories, file systems, and databases, to store configuration files.
Spring Cloud Config Client:
Client applications use this to fetch their configurations from the Config Server.
Spring Boot Actuator:
Provides endpoints to monitor and manage applications, including the ability to refresh configurations dynamically. 

Implementation Steps
Set up the Config Server:
Create a new Spring Boot application and add the spring-cloud-config-server dependency. Annotate the main class with @EnableConfigServer. Configure the location of the configuration files, typically a Git repository, using properties like spring.cloud.config.server.git.uri in the application.properties file. 
Set up Config Clients:
Add the spring-cloud-starter-config dependency to the client applications. Configure the location of the config server using spring.cloud.config.uri in the bootstrap.properties file or through environment variables. 
Dynamic Configuration Refresh:
Use Spring Boot Actuator to expose endpoints that allow clients to refresh their configurations without restarting. 

Benefits
Centralized Management:
Configuration properties are managed in one place, simplifying updates and ensuring consistency.
Dynamic Updates:
Changes to configurations can be applied without restarting applications, improving flexibility and operational efficiency.
Environment Segregation:
Configurations can be managed separately for different environments (e.g., development, testing, production).
Version Control:
When using Git as a backend, configuration changes are version-controlled, making it easy to track and revert changes.
Security:
Sensitive configuration data can be managed securely, with options for encryption and access control.
Centralized configuration management with Spring Boot and Spring Cloud Config is crucial for microservices architectures, enabling scalability, maintainability, and adaptability to changing environments.

----------------------------------------------------------------------------------

RestTemplate is a synchronous client in Spring Framework used for making HTTP requests to RESTful web services. It simplifies the process of interacting with APIs by abstracting the complexities of HTTP requests and responses.

Key Features:

Synchronous Communication:
It operates on a request-response model, blocking the calling thread until a response is received.

HTTP Method Support:
It supports various HTTP methods, including GET, POST, PUT, DELETE, and PATCH. 

Data Binding:
It integrates with Spring's data binding and conversion capabilities, enabling automatic mapping of request and response bodies to Java objects.

Customization:
It allows for customization through interceptors, error handlers, message converters, and request factories. 

Error Handling:
It provides built-in error handling mechanisms.

How to use it in Spring Boot:
Configuration: A RestTemplate bean is typically configured in a Spring configuration class.
Usage: Use methods like getForEntity(), postForEntity(), put(), delete(), and exchange() to make requests.
Response Handling: Handle responses by extracting data, status codes, and headers.

Code :
import org.springframework.http.ResponseEntity;
import org.springframework.web.client.RestTemplate;

public class Example {

    public static void main(String[] args) {
        RestTemplate restTemplate = new RestTemplate();
        String url = "https://example.com/api/data";

        // GET request
        ResponseEntity<String> response = restTemplate.getForEntity(url, String.class);
        System.out.println("Response Body: " + response.getBody());
        System.out.println("Status Code: " + response.getStatusCode());
    }
}


Configure Timeout - We can configure RestTemplate to time out by simply using ClientHttpRequestFactory:

There are four different types of timeouts we can configure:

Connect Timeout – the time to wait for the HTTP connection to be established. We configure this in RequestConfig
Read Timeout – the time the client should wait for the server to respond. We configure this in RequestConfig
Socket Timeout – the connection timeout for SSL handshakes or CONNECT requests. We configure this in SocketConfig
Connection Request Timeout – the amount of time to wait when requesting a connection from RequestConfig‘s connection manager

Code :

RestTemplate restTemplate = new RestTemplate(getClientHttpRequestFactory());

ClientHttpRequestFactory getClientHttpRequestFactory() {
    int timeout = 5;
    HttpComponentsClientHttpRequestFactory clientHttpRequestFactory = new 
      HttpComponentsClientHttpRequestFactory();
    clientHttpRequestFactory.setConnectionRequestTimeout(timeout*1000);
    clientHttpRequestFactory.setConnectTimeout(timeout*2000);
    clientHttpRequestFactory.setReadTimeout(timeout*3000);
    return clientHttpRequestFactory;
}
https://www.baeldung.com/rest-template
----------------------------------------------------------------------------------
How to enable 2nd level Caching 

A second-level cache is SessionFactory-scoped, meaning it’s shared by all sessions created with the same session factory. When an entity instance is looked up by its id (either by application logic or by Hibernate internally, e.g., when it loads associations to that entity from other entities), and second-level caching is enabled for that entity, the following happens:

If an instance is already present in the first-level cache, it’s returned from there.
If an instance isn’t found in the first-level cache, and the corresponding instance state is cached in the second-level cache, then the data is fetched from there and an instance is assembled and returned.
Otherwise, the necessary data are loaded from the database and an instance is assembled and returned.
Once the instance is stored in the persistence context (first-level cache), it’s returned from there in all subsequent calls within the same session until the session is closed, or the instance is manually evicted from the persistence context. The loaded instance state is also stored in the L2 cache if it wasn’t already there.

To enable the second-level cache in Hibernate, you need to configure a cache provider, enable the second-level cache, and then configure caching for specific entities. This involves setting properties in your Hibernate configuration file, adding cache provider dependencies to your project, and potentially creating a cache configuration file (like ehcache.xml). 
Here's a breakdown of the steps:

1. Choose and Add a Cache Provider:
Hibernate supports various cache providers like EHCache, Hazelcast, Infinispan, and others. 
Add the necessary dependencies to your project (e.g., for Maven, add the dependency for EHCache or Hazelcast). 
For instance, if using EHCache, you'd add the hibernate-ehcache and ehcache-core dependencies. 

2. Configure Hibernate Properties:
Set hibernate.cache.use_second_level_cache to true to enable the second-level cache. 
Set hibernate.cache.region.factory_class to the fully qualified class name of your chosen cache provider's RegionFactory (e.g., org.hibernate.cache.ehcache.EhCacheRegionFactory for EHCache). 
Consider setting hibernate.cache.use_query_cache to true if you want to cache query results as well. 

3. Configure Cache Regions for Entities:
Annotate your entity classes with @Cacheable (from javax.persistence.Cacheable) to enable caching for them. 
Specify the caching strategy using the @Cache annotation (e.g., READ_WRITE for read-mostly data). 
For example: @Cacheable @Cache(usage = CacheConcurrencyStrategy.READ_WRITE) public class MyEntity { ... }. 

4. Configure the Cache Provider (if needed):
Some providers, like EHCache, require a separate configuration file (e.g., ehcache.xml) to define cache regions, eviction policies, etc.
Place this file in your classpath. 

5. Example (using EHCache):

    <dependency>
        <groupId>org.hibernate</groupId>
        <artifactId>hibernate-ehcache</artifactId>
        <version>${hibernate.version}</version>
    </dependency>
    <dependency>
        <groupId>net.sf.ehcache</groupId>
        <artifactId>ehcache</artifactId>
        <version>${ehcache.version}</version>
    </dependency>

hibernate properties.

    hibernate.cache.use_second_level_cache=true
    hibernate.cache.region.factory_class=org.hibernate.cache.ehcache.EhCacheRegionFactory
    hibernate.cache.use_query_cache=true


@Entity
@Cacheable
@org.hibernate.annotations.Cache(usage = CacheConcurrencyStrategy.READ_WRITE)
public class Foo {
    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    @Column(name = "ID")
    private long id;

    @Column(name = "NAME")
    private String name;
    
    // getters and setters
}


Cache Concurrency Strategy
Based on use cases, we’re free to pick one of the following cache concurrency strategies:

READ_ONLY: Used only for entities that never change (an exception is thrown if an attempt to update such an entity is made). It’s very simple and performative. It’s suitable for static reference data that doesn’t change.
NONSTRICT_READ_WRITE: Cache is updated after the transaction that changed the affected data has been committed. Thus, strong consistency isn’t guaranteed, and there’s a small time window in which stale data may be obtained from the cache. This kind of strategy is suitable for use cases that can tolerate eventual consistency.
READ_WRITE: This strategy guarantees strong consistency, which it achieves by using ‘soft’ locks. When a cached entity is updated, a soft lock is stored in the cache for that entity as well, which is released after the transaction is committed. All concurrent transactions that access soft-locked entries will fetch the corresponding data directly from the database.
TRANSACTIONAL: Cache changes are done in distributed XA transactions. A change in a cached entity is either committed or rolled back in both the database and cache in the same XA transaction.

----------------------------------------------------------------------------

App.properties vs app.yaml spring boot

In Spring Boot, both application.properties and application.yaml (or .yml) files are used for externalized configuration, allowing you to define application-related properties and settings. While they serve the same fundamental purpose, they differ in their syntax and structure.

application.properties:

Syntax: Uses a simple key-value pair format, with each property on a new line.

Code

    server.port=8080
    spring.datasource.url=jdbc:mysql://localhost/mydb

Structure: Sequential, with no inherent hierarchy or nesting.
Readability: Can become less readable for complex configurations with many related properties.
Legacy Compatibility: Often preferred when migrating from older Spring applications or systems that traditionally use properties files.
application.yaml (or .yml):
Syntax: Uses YAML (YAML Ain't Markup Language) syntax, which is indentation-based and supports hierarchical structures.
Code

    server:
      port: 8080
    spring:
      datasource:
        url: jdbc:mysql://localhost/mydb

Structure:
Hierarchical and nested, making it suitable for organizing complex configurations.
Readability:
Generally considered more human-readable and organized for larger configurations due to its structured nature.
Features:
Supports more advanced data types like lists and maps directly within the file.
Multi-document Support:
YAML supports storing multiple documents within a single file, which can be used to define different profiles within the same configuration file.

Which to choose?
The choice between .properties and .yaml largely depends on personal preference and the complexity of your application's configuration. 
application.properties
is suitable for simpler configurations or when maintaining compatibility with existing systems.

application.yaml
is generally preferred for more complex applications with extensive and hierarchical configurations due to its improved readability and structure.
Spring Boot provides robust support for both formats, allowing you to use whichever best suits your project's needs. If both files are present, application.properties typically takes precedence for conflicting properties. 
------------------------------------------------------------------------------------------------------
Log Method
Trace - Only when I would be "tracing" the code and trying to find one part of a function specifically.
Debug - Information that is diagnostically helpful to people more than just developers (IT, sysadmins, etc.).
Info - Generally useful information to log (service start/stop, configuration assumptions, etc). Info I want to always have available but usually don't care about under normal circumstances. This is my out-of-the-box config level.
Warn - Anything that can potentially cause application oddities, but for which I am automatically recovering. (Such as switching from a primary to backup server, retrying an operation, missing secondary data, etc.)
Error - Any error which is fatal to the operation, but not the service or application (can't open a required file, missing data, etc.). These errors will force user (administrator, or direct user) intervention. These are usually reserved (in my apps) for incorrect connection strings, missing services, etc.
Fatal - Any error that is forcing a shutdown of the service or application to prevent data loss (or further data loss). I reserve these only for the most heinous errors and situations where there is guaranteed to have been data corruption or loss.

-----------------------------------------------------------------------------------------------------
how to enable logging in spring boot

Enabling logging in Spring Boot applications involves configuring the logging framework, typically Logback (the default), or others like Log4j2.
1. Setting Logging Levels in application.properties:
The most common way to enable and control logging levels is through the application.properties or application.yml file.

# Set the root logging level
logging.level.root=INFO

# Set a specific package's logging level
logging.level.com.example.myapp=DEBUG


2. Using Command-Line Arguments:
You can temporarily enable debug or trace logging for specific loggers or the entire application when starting it from the command line:

java -jar myapp.jar --debug
java -jar myapp.jar --logging.level.com.example.myapp=TRACE


3. Customizing Logback Configuration (logback-spring.xml):
For more advanced logging configurations, such as custom appenders, log patterns, or file-based logging, create a logback-spring.xml file in your src/main/resources directory.

<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <include resource="org/springframework/boot/logging/logback/base.xml"/>

    <logger name="com.example.myapp" level="DEBUG"/>

    <appender name="FILE" class="ch.qos.logback.core.FileAppender">
        <file>logs/myapp.log</file>
        <encoder>
            <pattern>%d{yyyy-MM-dd HH:mm:ss.SSS} [%thread] %-5level %logger{36} - %msg%n</pattern>
        </encoder>
    </appender>

    <root level="INFO">
        <appender-ref ref="FILE"/>
    </root>
</configuration>

4. Using a Logger Instance in Your Code:
To emit log messages from your application code, obtain a logger instance using SLF4J:


import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class MyService {
    private static final Logger logger = LoggerFactory.getLogger(MyService.class);

    public void doSomething() {
        logger.info("Doing something important.");
        logger.debug("Debug message for internal logic.");
        logger.error("An error occurred!");
    }
}
