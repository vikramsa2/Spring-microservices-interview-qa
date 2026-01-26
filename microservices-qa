xWhat are Microservices?
--------------------------
Microservices is an architecture in which the application performs as a loosely coupled service that can be developed, deployed, and maintained independently. Each service in this architecture is called a Microservice.

In Microservices, each service performs a different and unique function.
Through APIs it communicates with other services by focusing on the business strategies.
Different microservices can be used for different architecture and languages.

When and Why to use Microservices?
--------------------------------------

For large or complex projects microservices are the best choice for scalability, flexibility, and faster development with evolving requirements. Microservices are useful when the application or our project needs to be more scalable and manageable or requires more resources.

Microservices are ideal when the monolithic applications need to be optimized and modernized.
Each service can be independently developed, deployed, and maintained.
To reduce time, for scalability, fast development, low cost, and cloud-native development microservices are ideal.
We should not use microservices for simple applications which can be managed by monolithic architecture.

Explain the workings of Java Microservices Architecture
--------------------------------------------------------

In Java Microservices architecture, an application is divided into small processes or we can call them sub-processes. Each process runs on its functionality. All the sub-processes communicate with each other through small protocols. It manages better scalability and coordination between services.

What are the Pros and Cons of Java Microservices?
--------------------------------------------------

There are so many benefits and drawbacks in Java Microservices architecture.

Pros:
We can use different technologies using microservices.
It takes care of the security of each service.
More than one service can be parallelly developed and deployed.
Services are independently managed.
Better scalability and agility.

Cons:
Communication between microservices can be complex.
Large numbers of service management is difficult.
Handling microservices with different business requirements is a tough task.
So many configurations have to do which increases efforts.
Network maintenance is difficult.
Complex development and Security issues.

--------------------------------------------------
How to build a scaleable application

1. Design for Scalability:
a.Small, Independent Services:
Create microservices that are small, focused, and loosely coupled. Each service should handle a specific business capability.

Stateless Services:
Design services to be stateless, which allows for easy scaling by adding more instances.

API Gateway:
Use an API gateway to handle all external requests and route them to the appropriate microservices. This provides a single entry point and simplifies client interactions.

Database per Service:
Each microservice should have its own database or data store. This allows for independent scaling and reduces the risk of data conflicts.

2. Implement Scalability Techniques:
Horizontal Scaling:
Use horizontal scaling to handle increased load by adding more instances of each microservice.
Load Balancing:
Distribute traffic across multiple instances of a microservice using a load balancer.
Caching:
Implement caching to reduce database load and improve response times.
Message Queues:
Use message queues to handle asynchronous communication between microservices. This improves resilience and allows services to operate independently.
Read Replicas:
Implement read replicas for databases to handle read operations, reducing the load on the primary database.
Containerization:
Use Docker to package microservices into containers. This makes it easier to deploy and scale them across different environments.
Orchestration:
Use Kubernetes to manage and orchestrate microservices. Kubernetes provides features such as auto-scaling, load balancing, and service discovery.

3. Ensure Resilience and Monitoring:
Service Discovery:
Implement service discovery to allow microservices to locate each other dynamically.
Centralized Configuration:
Use a centralized configuration server to manage application configurations. This makes it easier to update configurations without restarting services.
Monitoring:
Monitor key metrics such as CPU usage, memory usage, and response times to identify performance bottlenecks and potential issues.
Resilience Patterns:
Implement resilience patterns such as circuit breakers, retries, and timeouts to handle failures gracefully.

4. Development and Deployment:
CI/CD Pipelines: Use CI/CD pipelines to automate the build, test, and deployment processes.
Cloud Platforms: Consider using cloud platforms such as AWS, Azure, or Google Cloud to host microservices. These platforms provide the infrastructure and services needed to build and scale microservices applications.

5. Technologies:
Spring Boot: Use Spring Boot to build microservices quickly and easily.
Spring Cloud: Use Spring Cloud for features such as service discovery, API gateway, and centralized configuration.
Docker: Use Docker to package microservices into containers.
Kubernetes: Use Kubernetes to manage and orchestrate microservices.
Eureka: Use Eureka for service discovery.
Spring Cloud Gateway: Use Spring Cloud Gateway for the API gateway.
Apache Kafka: Use Apache Kafka for message queuing.
Prometheus and Grafana: Use Prometheus and Grafana for monitoring.
By following these steps, you can build a scalable and resilient Spring Boot microservices application that can handle increasing load and changing requirements.

--------------------------------------------------
What are the main features of Java Microservices?
--------------------------------------------------

Deployment: It breaks an application into small services, because of this it is possible to deploy and develop each of these services independently.
Decentralization: Data storage management is decentralized. Each of the services has its own data related to a particular business functionality.
Loosely Coupled: If a single process fails, it will not affect the other services and the entire system.
Security: It provides authentication and authorization based on the Role-based access model (RBAC).
Scalable: Based on the requirements, services can be scaled which results in better scalability.

What is Monolithic architecture?
---------------------------------

A monolithic architecture-based application is built as a single unit means inside a single code base, all the -functionality and modules of the application are available.

Before microservices, all modules were there in a single project.
It supports tightly coupled architecture.
Here, we have a server. The server can be Tomcat, jetty, or any type.
In this server, we have deployed our application.
Inside this web application, we need to deploy all the modules of an application.
The outcome will be a WAR file. Only if we deploy the war file, these modules will be available.

Explain SOA.
--------------

SOA refers to Service-Oriented Architecture.
     This SOA architecture is a collection of multiple services.
     These multiple services do communicate with each other by using some standardized protocols.
     Also in this design approach, applications are build as a collection of services that are loosely coupled.
 
It communicates with each service over a network and then implements a specific business function. The communication could be the normal passing of data or more than two services sharing some common activity or any type of coordination.


What is the difference between Monolithic, SOA, and Microservices Architecture?
---------------------------------------------------------------------------------

Below are the basic differences between the Monolithic, SOA, and Microservices Architecture.

Features	Monolithic					SOA							Microservices
Structure	A single application where all software  Collection of services and loosely coupled.	Collection of small services and services
		components are assembled and tightly 							independently deployable.
		coupled.	

 
Communication	Within the same application, 		Using some standardized protocols,		Through some lightweight protocols, 
		components communicate with 		services communicate with each other.		all the services communicate with each other.
		each other.	
 
Scalability     Scaling is required according 		All services can be scaled independently.	All the services can be scaled independently
		to the needs of the entire 								 according to the business requirement.
		application.	
	

Development    It maintains centralized			It also maintains centralized development	It maintains decentralized development
and 	       development and components deployed      and here the services are deployed		and services deployed independently.
Deployment     as a single unit.			as monolithic applications.	
  	
  
 
Explain the design patterns of Java Spring Boot Microservices.
---------------------------------------------------------------

	Service Registry and Discovery: Services automatically register in a central registry, allowing others to identify and interact with them dynamically.

	API Gateway: It acts as a customer entry point and forwards requests to appropriate microservices to provide additional functionality such as authentication and rate limits.

	Circuit Breaker: It monitors the availability of services and protects from failures by sending requests or by providing responses if service is unavailable.

	CQRS (Command Query Responsibility Segregation): It separates the read and write operations. Also, it optimizes each and every operation separately for efficiency.

	Saga Pattern: It manages distributed tasks by organizing a sequence of local transactions.

	Database per service: Each of the services has separate databases. This ensures data isolation and also enables scaling and individual development.

	Asynchronous messaging: Each services communicate with each other through message queues like Kafka or RabbitMQ.


What are the Main Components of Java Spring Boot Microservices?
-----------------------------------------------------------------
The main components of Java Spring Boot Microservices include:
Services, Service Registry, API Gateway, Cloud Infrastructure, Containerization and Orchestration, Message Broker, Security, Monitoring


Name three commonly used tools for Java Spring Boot Microservices.
----------------------------------------------------------------------

There are different tools used for Java Spring Boot Microservices, some important tools are,
	Docker: This is a containerization tool that allows developers to put applications and their dependencies in a lightweight container, and provide stability across multiple environments.
	Kubernetes: This is an open-source container orchestration tool and it automates the scaling, deployment, and management of containerized applications. It offers features like service discovery, load balancing etc.
	Spring Cloud: This is a framework in the Spring ecosystem for building microservice-based applications. It is used to develop cloud-native applications. It offers features like service discovery, configuration management, circuit breakers etc.


How do Microservices Communicate with each other?
---------------------------------------------------
In Microservices, multiple services run independently. Services communicate with each other through,
	HTTP/REST: These are light-weight protocols used for perform communication between two services.
	Message queues: Message queues such as Kafka or RabbitMQ used to make connection.
	RPC (Remote Procedure Call) Framework: RPC frameworks such as gRPC uses in services for communication purposes.
These methods of communication enable loosely coupled interaction, scalability, and flexibility in distributed systems.
For more details please refer to this article: How do Microservices Communicate With Each Other?


How to Process the Request and Response between Two Services?
---------------------------------------------------------------

By establishing communication between the two services, microservices can handle requests and responses between any two services using XML (Extensible Mark-up Language) and JSON (JavaScript Object Notation).
	XML and JSON are data exchange formats and it helps to generate requests and responses between two services.
	Most important thing is the data exchange format and both the services have to know the data exchange format to request and respond accordingly.
	If we compare both formats, JSON is very simple to use in Microservices.


How to Register Java Microservices Using Netflix Eureka?
---------------------------------------------------------

The Eureka is the Netflix service discovery, consists of a discovery server and a client. The server can be configured and deployed to maximize performance, with each server copying the status of registered services to others. To Register and Discover Microservices Using Netflix Eureka we have to develop one Service Discovery and one Microservice.
	Developing Microservice or Eureka Client
	Developing Service Discovery or Eureka Server
For more details please refer to this article: 

How to Register Microservices Using Netflix Eureka?

To register microservices with Netflix Eureka, you'll need to set up a Eureka server, then configure your microservices as clients, adding the spring-cloud-starter-netflix-eureka-client dependency and annotating the main class with @EnableEurekaClient. 
Here's a more detailed breakdown:
1. Setting up the Eureka Server:
Add the dependency: Include the spring-cloud-starter-netflix-eureka-server dependency in your Eureka server project. 
Enable Eureka Server: Annotate your main application class with @EnableEurekaServer. 
Configure the server: Configure the server's port (default is 8761) and other settings in your application.properties file. 
2. Configuring Microservices as Eureka Clients:
Add the dependency:
Include the spring-cloud-starter-netflix-eureka-client dependency in each microservice project.
Enable Eureka Client:
Annotate the main application class of each microservice with @EnableEurekaClient.
Configure the client:
In the application.properties file of each microservice, specify the Eureka server's address using the eureka.client.serviceUrl.defaultZone property.
Example: eureka.client.serviceUrl.defaultZone=http://localhost:8761/eureka/
Register the service:
When the microservice starts, it will automatically register itself with the Eureka server. 
3. Accessing the Eureka Dashboard:
Navigate to the Eureka dashboard in your web browser by going to http://localhost:8761 (or the port you specified).
You should see the registered microservices listed in the dashboard

What is Client Side Service Discovery in Java Microservices and Provide Some Examples of It?
---------------------------------------------------------------------------------------------
In microservices, Service discovery refers to the process of dynamically locating and connecting to available services within a distributed system.
	In a microservice system, applications perform multiple tasks and that are composed of many independently deployable services.
	Service discovery is critical to facilitate communication between these different services.
	If we put Service Discovery in client side then we called it as Client Side Service Discovery.
Example:
	Netflix Eureka
	Zookeeper
	Consul
For more details please refer to this article: Client Side Service Discovery in Microservices


What is Server Side Service Discovery in Java Microservices and Provide Some Examples of It?
-----------------------------------------------------------------------------------------------
In microservices, Service discovery refers to the process of dynamically locating and connecting to available services within a distributed system.
	In a microservice system, applications perform multiple tasks and that are composed of many independently deployable services.
	Service discovery is critical to facilitate communication between these different services.
	If we put Service Discovery in server side then we called it as Server Side Service Discovery.
Example:
	NGNIX
	AWS ELB
For more details please refer to this article: Server Side Service Discovery in Microservices


Why Use Spring Cloud for Microservices Development?
-----------------------------------------------------
Spring Cloud is a project under which we have many sub-projects. We can solve all these problems with those sub-projects.
	Spring Cloud Config Server
	Service registration and discovery using Eureka
	Spring Cloud LoadBalancer
	resilience4j-ratelimiter
	Circuit Breakers Pattern


Explain 5 Major Challenges and Solutions of Java Spring Boot Microservices Architecture.
-----------------------------------------------------------------------------------------
There are 5 challenges are mentioned below with solutions that we might face while developing microservices applications.

	Challenge 1: Service Configuration Management 
	Solution: Spring Cloud Config Server centralizes configuration management for microservices.
	
	Challenge 2: Service Discovery and Registration 
	Solution: Eureka enables dynamic service discovery and registration.
	
	Challenge 3: Load Balancing Across Microservices 
	Solution: Spring Cloud LoadBalancer distributes traffic evenly among microservice instances.
	
	Challenge 4: Resilience and Fault Tolerance 	
	Solution: resilience4j-ratelimiter implements rate limiting to maintain stability under heavy load.
	
	Challenge 5: Handling Failures and Circuit Breakers 
	Solution: Circuit Breaker pattern with tools like Hystrix provides fault isolation and fallback mechanisms.


Tell Some Major Reasons to Choose Spring Boot For Microservices Development
----------------------------------------------------------------------------
Here are some major reason to Choose Spring Boot For Microservices Development.
	Embedded Server
	Support Load Balancer
	Auto Configuration
	Minimal Code using Annotations
	Loose Coupling
	Dependency Management
	Open Source
For more details please refer to this article: Major Reasons to Choose Spring Boot For Microservices Development

What is Circuit Breaker Pattern in Java Microservices?
-------------------------------------------------------
Circuit Breaker pattern in microservices follows fault-tolerance mechanism. It monitors and controls the interaction between different services. It dynamically manages service availability by temporarily canceling requests for failed services, prevents system overloading, and ensures graceful degradation in distributed environments. Circuit Breaker pattern typically operates in three basic states: Closed, Open, and Half-Open.
Here are some Characteristics of Circuit Breaker pattern:
	Fault Tolerance
	Resilience
	Monitoring
	Failure Isolation
	Fallback Mechanism
	Automatic Recovery


--------------------------------------------------------------------------
Explain Different Deployment Techniques to Deploy Java Microservices.
-----------------------------------------------------------------------
There are different ways to deploy Microservices. Some of them are mentioned below:
	Single Machine, Multiple Services: Buy a server and run microservices as services.
	Multiple Machines, Multiple Services: When application exceeds the capacity of the server, we can upgrade the server by scaling up (Add more Servers).
	Containerization: Each microservices runs independently by enabling flexibility and scaling as per demand.
	Orchestrators: It distributes the workload of a container over a group of servers. (Ex: Kubernetes)
	Serverless Deployment: Processes or containers use cloud to run code on demand.


What is the Main role of Docker in Microservices and How to deploy microservices in Docker?
--------------------------------------------------------------------------------------------
The main role of Docker in microservices is to provide containerization, which allows each microservice with its dependencies to coordinate with the runtime environment, ensuring stability in unique environments.
Steps to deploy microservices in Docker:
	step 1: Containerize each microservice by creating a Dockerfile specifying the application’s dependencies and runtime configuration.
	step 2: Build Docker images for each microservice using the docker build command.
	Step 3: Push the built Docker images to a Docker registry such as Docker Hub or a private registry.
	Step 4: Create Docker Compose or Kubernetes manifests defining the configuration for deploying and orchestrating the microservices.
	Step 5: Deploy the Dockerized microservices using Docker Compose or Kubernetes by running docker-compose up or applying the Kubernetes manifests respectively.
	Step 6: Monitor and manage the deployed microservices using Docker CLI commands or Kubernetes dashboard.


How to Deploy Java Spring Boot Microservices in AWS?
-------------------------------------------------------
To deploy our microservices application in AWS (Amazon Web Services), we need to follow the below steps.
	Step 1: In the first step, open the AWS Management Console and then go to EC2.
	Step 2: After that, click on theLoad Balancersand create a new Application Load Balancer. Also, create a new target group associated with that load balancer. Then define the target group targets (ECS instances) and health checks.
	Step 3: Now, in AWS Management Console, go to ECS and create a new ECS cluster.
	Step 4: Then choose the networking options and click on next. 
		Configure the cluster give name to the cluster.
		Then create ECS Task and click on the repository.
		Now, configure the repository and make sure it is private.	
		Lastly, create the Task Definitions.
	Step 5: Now update the ECS Task.

===================================================================================================
AppDynamics to see the logs

Here's a breakdown of the golden signals: 
Latency:
The time it takes for a system to respond to a request. Monitoring latency helps identify slow or unresponsive services.
Traffic:
The volume of requests a system is handling. Tracking traffic helps understand the load on the system and identify potential bottlenecks.
Errors:
The rate of failed requests. Monitoring error rates helps identify issues that are preventing users from accessing the service.
Saturation:
The degree to which a system is using its resources. Monitoring saturation helps identify when a system is reaching its capacity and needs to be scaled.

These four signals are considered "golden" because they directly impact the user experience and are crucial for understanding the health of a system. By monitoring these signals, teams can quickly identify issues, troubleshoot problems, and ensure the reliability and performance of their systems. 
In addition to monitoring, the golden signals are used for: 
Alerting: Setting up alerts based on these signals to notify teams of potential problems.
Troubleshooting: Using the signals to pinpoint the root cause of issues.
Tuning and Capacity Planning: Using the signals to optimize system performance and plan for future growth.
--------------------------------------------------------------------------------------------------------------

1. Setup and Configuration
Install Jenkins and required plugins: Git, Maven, Pipeline, SonarQube Scanner.
Configure tools in Jenkins: JDK, Maven, Git, and SonarQube server with authentication.

2. Create a Pipeline Job
I create a Pipeline job in Jenkins and link it to the Git repository.
I use a Jenkinsfile stored in the repo to define the pipeline stages.

3. Define Pipeline Stages
"The pipeline typically includes the following stages:"

Checkout: Pulls the latest code from Git.
Build: Uses Maven to compile and package the application (mvn clean install).
SonarQube Analysis: Runs mvn sonar:sonar to analyze code quality and test coverage.
Quality Gate: Waits for SonarQube to return a pass/fail result based on configured thresholds.
Deploy: If the quality gate passes, the application is deployed (e.g., via shell script or CI/CD tool).
Post Actions: Publishes JUnit test results to Jenkins for visibility.

4. Automation and Triggers
I configure webhooks or polling to trigger the pipeline automatically on code changes.

5. Monitoring and Feedback
I monitor the pipeline via Jenkins UI and use SonarQube dashboards to track code health and coverage.
If the quality gate fails, the pipeline stops, ensuring only high-quality code is deployed.

------------------------------------------------------------------------------------------
Jenkins Pipeline

pipeline {
    agent any

    tools {
        maven 'Maven 3.8.6' // Name as configured in Jenkins
        jdk 'JDK 11'        // Name as configured in Jenkins
    }

    environment {
        SONARQUBE = 'SonarQubeServer' // Name as configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://your-git-repo-url.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQubeServer') {
                    sh 'mvn sonar:sonar'
                }
            }
        }

        stage('Quality Gate') {
            steps {
                timeout(time: 1, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }

        stage('Deploy') {
            steps {
                // Replace with your deployment logic
                sh './deploy.sh'
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
    }
}
