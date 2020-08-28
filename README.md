# Learn Microservices with Spring Boot - Chapter 8c (3/4)

This repository contains the source code of the practical use case described in the book [Learn Microservices with Spring Boot (2nd Edition)](https://tpd.io/book-extra).

The book follows a pragmatic approach to building a Microservice Architecture. You start with a small monolith and examine the _pros_ and _cons_ that come with a move to microservices. 

## Chapter 8 version 3/4

The Chapter 8's source code is divided into four parts for a better understanding of how the system evolves when we start introducing _Common Patterns in Microservice Architectures_.

In this third part, we introduce Centralized Configuration, supported by Consul KV. This pattern allows us to keep a different configuration for our microservices per environment.

![Logical View - Chapter 8 3/4](resources/microservice_patterns-Config-Server.png)

The main concepts included in this first part of the chapter are:

* Why do we need a Configuration Server?
* Consul KV and its integration in Spring Boot via Spring Cloud Consul Configuration.
* Creating profile combinations in Consul KV.
* Trying out the configuration server in our system.

As usual, the book follows a hands-on approach, so you learn everything based on this microservice case study.

Check the [Book's Web Page](https://tpd.io/book-extra) to see the complete list of chapters.

## Running the app

Requirements:

* JDK 14+
* Node.js v13.10+
* npm 6.13.7+
* RabbitMQ 3.8.3+
* Consul 1.7.2+

1. You need a RabbitMQ server running. Run the server according to the instructions for your OS, for example:
    ```bash
    $ rabbitmq-server
    ```
1. You also need Consul up and running (in development mode). Follow the instructions for your OS, for example:
    ```bash
    $ consul agent -node=learnmicro -dev
    ```
1. To start the Multiplication microservice, you can use the command line with the included Maven wrapper:
    ```bash
    multiplication$ ./mvnw spring-boot:run
    ```
2. To start the Gamification microservice, you do the same from its corresponding folder:
    ```bash
    gamification ./mvnw spring-boot:run
    ```
3. To start the Gateway microservice, you do the same from its corresponding folder:
    ```bash
    gamification ./mvnw spring-boot:run
    ```
2. The React application can be started with npm. First, you need to download the dependencies with:
    ```bash
    challenges-frontend$ npm install
    ```
3. Then, you start the server with:
    ```bash
    challenges-frontend$ npm start
    ```

> **_Note:_**
> 
> In the [final version of our code](https://github.com/Book-Microservices-v2/chapter08d), we use Docker to start our complete system easily. However, it's not yet introduced at this point in the book, so we're starting all these components manually.

Once the backend and the fronted are started, you can navigate to `http://localhost:3000` in your browser and start resolving multiplication challenges.

## Playing with the config server

In this version, you can play with the config server using different scenarios. [Get the book](https://tpd.io/book-extra) for instructions on how to initialize the data using Consul KV.

If you want to see the config server in practice without loading data manually, jump to [version 8d](https://github.com/Book-Microservices-v2/chapter08d) where we use a Docker image to initialize the config server with some predefined values.

## Questions

* Do you have questions about how to make this application work?
* Did you get the book and have questions about any concept explained within this chapter?
* Have you found issues using updated dependencies?

Don't hesitate to create an issue in this repository and post your question/problem there. 

## About the book

Are you interested in building a microservice architecture from scratch? You'll face all the challenges of designing and implementing a distributed system one by one, and will be able to evaluate if it's the best choice for your system.

Visit [https://thepracticaldeveloper.com/learn-microservices-v2](https://tpd.io/book-extra) for all the details about the book.
