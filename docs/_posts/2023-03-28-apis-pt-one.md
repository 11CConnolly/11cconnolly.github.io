---
layout: post
title: What is an API?
date: Tue Mar 28 18:44:05 GMT 2023
categories:
---

APIs are one of the most fundamental concepts in programming. We hear about Twitter's API being increasingly locked down, new ChatGPT APIs being developed and made public to take advantage off, terms such as SOAP, REST, GraphQL, etc. This leads us to a question of what exactly is an API, and why should be care about them?

Very simply:

> An API is a way to talk to a program to get it to do something.

That's it.

APIs are a consistent, predefined [interface](https://techterms.com/definition/interface) or contract that let people who write programs get another program or system to do something. Different people will normally be able to do different things with APIs; certain methods will be available (exposed) to them depending on their permissions and they can e.g. get data that other people can't. It is important to remember that APIs are fundamentally aiming to solve some problem. They don't just exist for the sake of it. They exist to be used by someone, for some purpose.

Application - A program is doing it
Programming - A developer is using it
Interface - A consistent set of rules

With all of that being said, when you hear the term API around the web, most often this will be referring to a Web API whose purpose is to send or receive some data. To understand APIs the best way is to make your own. Second to that, we can look at the evolution of getting other someone else's computer to do something, and how we solve some of those problems that problem.

### Remote Procedure Calls, or, How Do I Get Your Computer To Do Something?
The fundamental problem when computers began to be networked was how do I get someone else's computer to do something? Whether that something is sending data back, performing some database read, or making a calculation. The idea of network operations of a client that initiates a request and a server that performs some action goes back at least to the 1970s with the early ARPANET. There were attempts to standardize the interface in these interactions, but what ended up happening was different services would have very different specifications for communicating with their API. One service would have a certain interface, another with another, and there was, in general, little consistency. There were language specific RPC interfaces, Application specific interfaces, and implementation specific interfaces which made if difficult to know exactly how to create APIs, and how exactly your API would communicate with another service.

### Order From The Chaos: REST
REST is a set of rules for creating applications to communicate over the Internet. The idea of REST is an worldwide consistent specification for querying and receiving data.

This comes in the form of using 5 main HTTP verbs:
- PUT / PATCH - edit some resource (either fully / partially)
- POST - create some resource
- DELETE - delete some resource
- GET - retrieve some resource

and HTTP status codes as indications:
- 200: OK
- 2XX - Successful request, resource created...
- 4XX - Client-side error (Bad request, resource doesn't exist...)
- 5XX - Server-side error

Rather than being procedure oriented as RPC are, REST is resource oriented and REST APIs send back data in the form of JSON and/or XML. There are a lot of standards floating around, but JSON has emerged as the easiest way to send data from services. So, rather then an individual specification for each and every application sending and receiving it's own form of data, we have a consistent and semantic way to query any resource on the planet, and get back information in a consistent format. When being built, RESTful services also must conform to [six architectural principles](https://www.webscrapingapi.com/rest-api-architecture-constraints).

### And The Rest
As we have said previously, APIs exist to solve some problem. Depending on the problem you're trying to solve, a different approach may be better, such as RPC, SOAP, GraphQL. Generally, RPCs are the better choice to enable communication between distributed systems and processing is a major factor. SOAP, or Simple Objects Access Protocol, is a communications protocol using XML with the API logic written in a consistent Web Description Language. Whilst this does provide a uniform interface, it ends up being slower and heavy-handed than many other approaches. On the other hand, GraphQL is a query language where the server defines the schema of the data and handles the data requests, and the client requests exactly the data that they need. Generally, it is a much faster and leaner query language, however each service has it's own schema to learn.


This is the end of Part 1, and for most developers just getting into things, this will be a good enough overview into hearing the term API blasted around the web.
