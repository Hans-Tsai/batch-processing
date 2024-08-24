# Creating a Batch Service

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Result](#result)
- [Reference](#reference)

## Introduction
- This is a batch processing service built using the Spring Batch framework, created based on the official documentation.

## Spring Batch architecture
![](./img/spring-batch-reference-model.png)

- A `Job` has one to many steps, each of which has exactly one `ItemReader`, one `ItemProcessor`, and one `ItemWriter`. A `job` needs to be launched (with `JobLauncher`), and metadata about the currently running process needs to be stored (in `JobRepository`).

## Features
- Import a CSV file.
- Convert it to a custom format (e.g. lowercase to uppercase).
- Output the results to a database.
- Get notified when the job completes.

## Installation
- Use [Spring Initializr](https://start.spring.io/) to set up this Spring Batch service project.
    - Dependency
        - **Spring Batch**
        - **HyperSQL Database**

## Usage
- Maven
    - Method 1: Run the application.
        ```bash
        ./mvnw spring-boot:run
        ```
      
    - Method 2: Build the **JAR** file, and then run the **JAR** file.
        ```bash
        ./mvnw clean package
        ```
      
        ```bash
        java -jar target/gs-batch-processing-0.1.0.jar
        ```
      
## Result
```console
Converting (Person[firstName=Jill, lastName=Doe]) into (Person[firstName=JILL, lastName=DOE])
Converting (Person[firstName=Joe, lastName=Doe]) into (Person[firstName=JOE, lastName=DOE])
Converting (Person[firstName=Justin, lastName=Doe]) into (Person[firstName=JUSTIN, lastName=DOE])
Converting (Person[firstName=Jane, lastName=Doe]) into (Person[firstName=JANE, lastName=DOE])
Converting (Person[firstName=John, lastName=Doe]) into (Person[firstName=JOHN, lastName=DOE])

Found <{Person[firstName=JILL, lastName=DOE]}> in the database.
Found <{Person[firstName=JOE, lastName=DOE]}> in the database.
Found <{Person[firstName=JUSTIN, lastName=DOE]}> in the database.
Found <{Person[firstName=JANE, lastName=DOE]}> in the database.
Found <{Person[firstName=JOHN, lastName=DOE]}> in the database.
```

## Reference
- [Spring Batch](https://docs.spring.io/spring-batch/reference/index.html)
- [Creating a Batch Service](https://spring.io/guides/gs/batch-processing)
    - [GitHub: gs-batch-processing](https://github.com/spring-guides/gs-batch-processing/tree/main?tab=readme-ov-file#what-you-will-build)