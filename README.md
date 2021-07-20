# Java Spring Boot
### Table of contents
- [General info](#general-info)
- [Technologies](#technologies)
- [Setup](#setup)
- [Things learned](#things-learned)
>- What spring boot is.
>- What inversion of control is.
>- Dependency injection.
>- POJOs.
>- JPA.
>- JPQL.
>- Query methods. 
- [Commands](#commands)


------------

### General info

This repository contains files and explanations of things learned in the Platzi's Java Spring Boot Course. This course taught about the principles of how spring boot works. It taught the basic annotations, configurations and structure of a project using spring boot and generally served as an introductory course. The project in this repository contains files that were used to practice all the basic annotations, structure and commands of spring boot and some other dependencies.

------------

### Technologies
- JDK11 (requieres installation)
- IntelliJ IDEA (requieres installation)
- Postman


**Dependencies:**
- Spring Boot Dev Tools 
- Spring Boot Starter Web
- H2 Database

------------

### Setup

###### IntelliJ IDEA 
- Go to https://www.jetbrains.com/idea/download/ and download the Community version

###### OpenJDK
- Go to https://www.oracle.com/java/technologies/javase-jdk11-downloads.html and download the according versio to your OS.
- Complete the installation process. 

#####  Postman
- Go to https://www.postman.com/downloads/ and click on the download the app button.
- Complete the installation process.

##### Spring Initializr
- Go to https://start.spring.io/ and configure the project with java 11 and maven.
- Click on the generete button and download the file. This file contains the Java Project which is going to be opened with Intellij IDEA.
- Extract the file.

**Within Intellij IDEA**

###### Dependencies:
- Spring Boot Dev Tools. Spring boot Starter Web. H2 Database. Copy the next code and insert it into the pom.xml file in the dependencies part of the code.
```java
<dependency>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-devtools</artifactId>
<optional>true</optional>
</dependency>

<dependency>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-starter-web</artifactId>
</dependency>

<dependency>
<groupId>com.h2database</groupId>
<artifactId>h2</artifactId>
<version>1.4.200</version>
<scope>runtime</scope>
</dependency>
```

------------
### Things learned
- What spring is. Its an application framework and inversion of control container for the Java platform. The frameworks core features can be used by any Java application, but there are extensions for building web applications on top of the Java EE platform.

- To create an application with spring boot.

- What Inversion of Control is. It means giving the control of creating and instantiating the spring beans to the Spring IOC container and the only work the developer does is configuring the beans in the spring xml file.

- Dependencies. An object with a functionality. They aim to work with other objects or functionalities

- POJOs. (Plain Old Java Object) is an acronym used by Java programmers to emphasize the use of simple classes that do not depend on a particular framework.

- IoC advantages.
>- Makes it easier to test your code. 
>- Useful when developing modular systems. You can replace components without requiring recompilation.
>- Makes easier the management of dependencies between objects.

- What a bean is. It is a component made in software that can be reused and that can be visually manipulated by a Java programming tool.

- Dependency injection. Dependency Injection is merely one concrete example of Inversion of Control. When writing a complex Java application, application classes should be as independent as possible. Dependency Injection helps in gluing these classes together and at the same time keeping them independent. For example, class A is dependent of class B. Class B will get injected into class A by the IoC.

- Spring boot annotations.

- To create and configure my own dependencies.

- To change ports and path.

- What a log is and how to use it.

- What JPA is. Java Persistence API is a collection of classes and methods to persistently store the vast amounts of data into a database which is provided by the Oracle Corporation

- JPQL. JPQL is a powerful query language that allows you to define database queries based on your entity model. Its structure and syntax are very similar to SQL. It doesn´t work with tables but with objects representing those tables. It supports queries and namedqueries. Example: 
```java
@Query("Select r from Reserva r where r.fechaIngresoRes =:fechaInicio and r.fechaSalidaReserva =: fechaSalida")
public List<Reserva> find(@Param("fechaInicio")Date fechaInicio, @Param("fechaSalida") Date fechaSalida);

@NamedQuery(name ="Cliente.findByIdentificacion", query="Select c from Cliente c where c.identificacionCli = ?1")
```

- Query methods are methods that find information from the database and are declared on the repository interface. Example findByDateOrderByNameDesc. It is very importatnt to use correctly camelcase.

- Pagination with spring boot.

------------
### Commands
|  Command | Function  |
| ------------ | ------------ |
| @Springbootapplication | Tells Spring Boot that a class manages the app.   |
| @Entitiy | Tells a java class that it is representing a table in the database.   |
| @Table  | Receives the name of the table to which our class is mapping.   |
| @Column  | Used when the name of our column is different from the name of the attribute of our table.   |
| @id  | Represents the primary key of the table inside the class.  |
| @GenerateValue  | Automatically generate values for the primary keys .   |
| @OneToMany @ManyToOne  | Represent existing relationships in tables but in classes.   |
| @Query    | Used to make native queries   |
| @Repository   | Tells the class that it interacts with the database |
| @Component   | Indicates that a class is a spring component  |
| @Autowired   | Spring manages objects that we haven't initialized creating them by itself. It is not necessary in newer versions. |
| @Service   | Indicates that a class is a business logic service.  |
| @RestController   | Tells spring that a class will be a controller of a rest API |
| @GetMapping    | To obtain information  |
| @Postmapping  | To save or update information  |
| @Deletemapping | To delete information |
| CrudRepository methods | save(), delete()|
| @Qualifier | Tells wich implementations is going to be used by a dependency |
| @Value | Brings values previously generated in properties files |
| @Bean | Object that is instantiated, assembled, and managed by a Spring IoC container|
| @Transactional | Prevents operations from be applied to the database if onlye a single operation fails|
| @PropertySource | Indicates the path of the proporties to be used |
