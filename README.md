# First-Java-CRUD

A simple CRUD (Create, Read, Update, Delete) web application written in Java.
It is based on the official Spring guide
[Creating CRUD UI with Vaadin](https://spring.io/guides/gs/crud-with-vaadin/).

The application manages a list of customers (first name, last name). You can:

- list all customers in a grid
- filter customers by last name
- add a new customer
- edit an existing customer
- delete a customer

Five sample customers are added on startup and printed to the console.

## Tech stack

- Java 17+
- Spring Boot 3.5
- Vaadin 24 (Flow, server-side Java UI)
- Spring Data JPA
- H2 in-memory database
- Maven (with Maven Wrapper)

## Requirements

- JDK 17 or newer (`java -version` to check)
- No Maven installation needed: the included Maven Wrapper downloads it automatically
- Internet connection on the first run (to download dependencies)

## How to run

Windows:

```
mvnw.cmd spring-boot:run
```

Linux / macOS:

```
./mvnw spring-boot:run
```

Then open http://localhost:8080 in your browser.

The first start can take a while, because Vaadin prepares its frontend.
Stop the application with `Ctrl+C`.

Note: the database is in-memory, so all changes are lost when the application stops.

## Project structure

```
First-Java-CRUD/
├── doc/                          screenshots and documentation
├── src/main/java/com/example/crud/
│   ├── CrudWithVaadinApplication.java   Spring Boot entry point, loads sample data
│   ├── Customer.java                    JPA entity (id, firstName, lastName)
│   ├── CustomerRepository.java          Spring Data JPA repository
│   ├── MainView.java                    main page ("/"): grid, filter, "New customer" button
│   └── CustomerEditor.java              form for creating / editing / deleting a customer
├── .mvn/wrapper/                 Maven Wrapper configuration
├── mvnw, mvnw.cmd                Maven Wrapper scripts
└── pom.xml                       Maven build file (dependencies)
```
