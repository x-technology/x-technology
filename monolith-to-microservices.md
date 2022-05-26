[![XTechnology - Technology is beautiful, let's discover it together!](https://user-images.githubusercontent.com/1259644/139526072-c2df5b3f-86b3-40eb-a91a-e51a307269ec.png)](https://xtechnology.dev/)

<style type="text/css">
  h1:first-child {
    display: none;
  }
  
  img[alt="andrew reddikh"] {
    filter: grayscale(100%);
  }

  img {
    max-width: 500px;
  }

  /* twitter button */
  .twitter-btn {
    width: 200px;
    display: inline-block;
    overflow: hidden;
    text-align: left;
    white-space: nowrap;
    vertical-align: top:
    zoom: 1;
    font-size: 13px;
    line-height: 26px;
    font-family: "Helvetica Neue",Arial,sans-serif;
  }
  .twitter-btn a {
    height: 28px;
    padding: 1px 10px 1px 9px;
    border-radius: 4px;
    position: relative;
    font-weight: 500;
    color: #fff;
    cursor: pointer;
    background-color: #1b95e0;
    border-radius: 3px;
    box-sizing: border-box;
    display: inline-block;
    text-decoration: none;
  }
  .twitter-btn a:hover {
    background-color: #0c7abf;
  }
  .twitter-btn a i {
    width: 18px;
    height: 18px;
    top: 4px;
    position: relative;
    display: inline-block;
    background: transparent 0 0 no-repeat;
    background-image: url(data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%2072%2072%22%3E%3Cpath%20fill%3D%22none%22%20d%3D%22M0%200h72v72H0z%22%2F%3E%3Cpath%20class%3D%22icon%22%20fill%3D%22%23fff%22%20d%3D%22M68.812%2015.14c-2.348%201.04-4.87%201.744-7.52%202.06%202.704-1.62%204.78-4.186%205.757-7.243-2.53%201.5-5.33%202.592-8.314%203.176C56.35%2010.59%2052.948%209%2049.182%209c-7.23%200-13.092%205.86-13.092%2013.093%200%201.026.118%202.02.338%202.98C25.543%2024.527%2015.9%2019.318%209.44%2011.396c-1.125%201.936-1.77%204.184-1.77%206.58%200%204.543%202.312%208.552%205.824%2010.9-2.146-.07-4.165-.658-5.93-1.64-.002.056-.002.11-.002.163%200%206.345%204.513%2011.638%2010.504%2012.84-1.1.298-2.256.457-3.45.457-.845%200-1.666-.078-2.464-.23%201.667%205.2%206.5%208.985%2012.23%209.09-4.482%203.51-10.13%205.605-16.26%205.605-1.055%200-2.096-.06-3.122-.184%205.794%203.717%2012.676%205.882%2020.067%205.882%2024.083%200%2037.25-19.95%2037.25-37.25%200-.565-.013-1.133-.038-1.693%202.558-1.847%204.778-4.15%206.532-6.774z%22%2F%3E%3C%2Fsvg%3E);
  }
  .twitter-btn a span {
    margin-left: 4px;
    white-space: nowrap;
    display: inline-block;
    vertical-align: top;
    zoom: 1;
  }
</style>

<div class="twitter-btn">
  <a href="https://twitter.com/XTechnology5/status/1513973177768157200"><i></i>
  <span>Tweet about Decompose</span></a>
</div>

# How to Decompose Monolith API into GRPC Microservices

The workshop focuses on concepts, algorithms, and practices to decompose a monolithic application into GRPC microservices. It overviews architecture principles, design patterns and technologies used to build microservices. It covers the theory of the GRPC framework and protocol buffers mechanism, as well as techniques and specifics of building isolated TypeScript services in the Node.js stack. The workshop includes a live use case demo of decomposing an API application into set of microservices. It fits the best architects, tech leads, and developers who want to learn microservices patterns.

## General

- 2 hours
- Advanced level
- Patterns - DDD, Microservices
- Technologies - GRPC, Protocol Buffers, Node.js, TypeScript, NestJS, Express.js, PostgreSQL
- Example structure - monorepo configuration, packages configuration, common utilities, demo service
- Practical exercise - build a currency converter service

### Prerequisites

- Good understanding of JavaScript or TypeScript
- Experience with Node.js and writing Backend applications
- [Preinstall Node.js, npm](https://nodejs.org/en/download/)
- [Preinstall Docker](https://docs.docker.com/get-docker/), [docker-compose](https://docs.docker.com/compose/install/)
- [Preinstall Protocol Buffer Compiler](https://grpc.io/docs/protoc-installation/)
- We prefer to use VSCode for a better experience with JavaScript and TypeScript (other IDEs are also ok)

### Instructors

[Alex Korzhikov](https://twitter.com/AlexKorzhikov) & [Andrew Reddikh](https://twitter.com/AndrewRedUK)

### Materials

- [Workshop Event - May 28, 2022 10:00 AM CET](#TODO)
- [Repository](https://github.com/x-technology/monolith-banking-app-splitting-to-micro-services)
- [Practical Exercises as Github Issues](https://github.com/x-technology/micro-services-infrastructure-pulumi-azure-devops/issues)

![repository-open-graph-template 1](https://user-images.githubusercontent.com/1259644/115153860-493a2880-a078-11eb-85c8-201b1512ee4b.png)

# Workshop Begins!

## Agenda

- [Introduction](#introduction)
  - [Who are we?](#who-are-we)
  - [What are we going to do today?](#TODO)
  - [Project Ecosystem](#project-ecosystem)
- [A way to decompose](#TODO)
  - Monolith
  - Microservice
  - Principles
  - Architecture Patterns
    - Strangler Application
    - DDD
    - Clean Architecture
  - Algorithm
- [Practice](#TODO)
- [Summary](#summary)

## Introduction

### Who are we?

#### Alex Korzhikov

![alex korzhikov](https://github.com/x-technology/PizzaScript/blob/main/assets/alex-black-white-open-source.png?raw=true)

Software Engineer, Netherlands

My primary interest is self development and craftsmanship. I enjoy exploring technologies, coding open source and enterprise projects, teaching, speaking and writing about programming - JavaScript, Node.js, TypeScript, Go, Java, Docker, Kubernetes, JSON Schema, DevOps, Web Components, Algorithms 👋 ⚽️ 🧑‍💻 🎧

- [AlexKorzhikov](https://twitter.com/AlexKorzhikov)
- [korzio](https://github.com/korzio)

#### Andrew Reddikh

[![andrew reddikh](https://andrew.red/photo.jpg)](https://andrew.red)

Software Engineer, United Kingdom

Passionate software engineer with expertise in software development, microservice architecture, and cloud infrastructure. On daily basis, I use Node.js, TypeScript, Golang, and DevOps best practices to build a better tech world by contributing to open source projects.

- [AndrewRedUK](https://twitter.com/AndrewRedUK)
- [mazahaca](https://github.com/mazahaca)

### What are we going to do today?

[⬆️ About](#TODO)

### Project Ecosystem

![Github Project Unknown](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)

#### [Bank Application](https://github.com/pietrzakadrian/bank-server) by [Adrian Pietrzak](https://twitter.com/PietrzakAdrian)

![Nest Icon](https://camo.githubusercontent.com/5f54c0817521724a2deae8dedf0c280a589fd0aa9bffd7f19fa6254bb52e996a/68747470733a2f2f6e6573746a732e636f6d2f696d672f6c6f676f2d736d616c6c2e737667)

#### [Nest Framework](https://nestjs.com/)

> A progressive Node.js framework for building efficient, reliable and scalable server-side applications

```ts
// modules
import { Module } from '@nestjs/common';
import { CatsModule } from './cats/cats.module';

@Module({
  imports: [CatsModule],
})
export class AppModule {}

// controllers
import { Controller, Get, Req } from '@nestjs/common';
import { Request } from 'express';

@Controller('cats')
export class CatsController {
  @Get()
  findAll(@Req() request: Request): string {
    return 'This action returns all cats';
  }
}
```

- [Nest Documentation](https://docs.nestjs.com/)
- `TypeScript` with Web Servers
  - `Angular` for Backend
  - Decorators, special types to control application flow
  - `Express` or `Fastify`
  - Dependency Injection, DDD, CQRS

#### [GRPC](./grpc.md)

<a href="https://grpc.io/"><img src="https://github.com/grpc/grpc-community/blob/main/PanCakes/Pancakes_Bandana.png?raw=true" width="500px" alt="grpc logo aka pancakes"/></a>

> gRPC Remote Procedure Calls, of course!

> [gRPC](https://grpc.io/docs/what-is-grpc/faq/) is a *modern, open source* *remote procedure call (RPC)* framework that can run anywhere. It enables *client and server* applications to communicate transparently, and makes it easier to build connected systems

![microservices graph](https://github.com/x-technology/mono-repo-nodejs-svc-sample/raw/main/docs/assets/graph.png)

- March 2015 🗓
- Google ➡️ Open Source
- Standardize Microservices Architecture, Framework & Infrastructure

![Architecture](https://grpc.io/img/landing-2.svg)

- Service Definitions (Protocol)
  - Protocol Buffers ⏭
- Client & Server
  - Generated Code (Stubs)
  - [10+ Languages](https://grpc.io/docs/languages/)
  - [Platforms & Environments](https://grpc.io/docs/platforms/) - Android, Web, Flutter
- Communication
- Authentication

```proto
// http://protobuf-compiler.herokuapp.com/
syntax = "proto3";

package hello;

service HelloService {
  rpc JustHello (HelloRequest) returns (HelloResponse);

  rpc ServerStream(HelloRequest) returns (stream HelloResponse);

  rpc ClientStream(stream HelloRequest) returns (HelloResponse);

  rpc BothStreams(stream HelloRequest) returns (stream HelloResponse);
}

message HelloRequest {
  string greeting = 1;
}

message HelloResponse {
  string reply = 1;
}
```

![client server communication](https://raw.githubusercontent.com/x-technology/mono-repo-nodejs-svc-sample/main/docs/assets/client-server-grpc.png)

#### Protocol Buffers

*An efficient technology to serialize structured data*

```proto
message Person {
  string name = 1;
  int32 id = 2;
  bool has_ponycopter = 3;
  // rule type name tag
  repeated uint64 vals = 4;
}
```

- [Protocol Buffers - Google Developers](https://developers.google.com/protocol-buffers/)
- [July 2008](https://github.com/protocolbuffers/protobuf/commit/40ee551715c3a784ea6132dbf604b0e665ca2def) 🗓
- Google ➡️ Open Source
- Typed `.proto` format
- Code Generation
  - `protoc` - the protocol buffers compiler
  - [10+ Languages](https://github.com/protocolbuffers/protobuf#protobuf-runtime-installation)
  - [Third-Party Add-ons for Protocol Buffers](https://github.com/protocolbuffers/protobuf/blob/master/docs/third_party.md)
- Services Description

```proto
syntax = "proto3";

package hello;

service HelloService {
  rpc SayHello (HelloRequest) returns (HelloResponse);
}

message HelloRequest {
  string greeting = 1;
}

message HelloResponse {
  string reply = 1;
}
```

#### Other

- Monorepo (`turborepo || nx || lerna`) *to migrate an application in real-time*
- Database (`PostgreSQL` and `TypeORM`)
- `Docker` and `docker-compose` *to start all components at once in configured network*
- [Github Actions](https://docs.github.com/en/actions/learn-github-actions/usage-limits-billing-and-administration) *to automate software workflows with world-class CI/CD*

## A way to decompose

[Melvin E. Conway's law, 1967](https://en.wikipedia.org/wiki/Conway%27s_law)

> Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure.

Application
  - handles HTTP requests,
  - executes business logic,
  - retrieves and updates database,
  - returns a JSON response

### Monolith

Application developed and deployed as a single unit which can sustain consistent state

> Simple to develop, test, deploy, and scale linearly all together!

Slow & difficult to
  - introduce changes, 
  - onboard developers, 
  - deploy, debug, and scale, 
  - maintain *Long Term Support* for technology stack

### Microservice

> An architectural pattern, affects an organization, process, and result!

![Microservice org benefits](https://microservices.io/i/successtriangle.png)

Application as a set of services that are
  - deliver business feature,
  - independently deployable,
  - owned by a small team,
  - follow single responsibility principle & granularity,
  - loosely coupled,
  - maintainable and testable,
  - exposes an API,
  - even used on FrontEnd!

Fast & easy to
  - deploy,
  - iterate & evolve,
  - onboard developers,
  - choose technology,
  - scale

### Goals, Principles, Requirements

- Deliver value in parallel and independently
- Experiment with business capabilities
- Grow number of teams

- Common Closure Principle
  - Self contained services
- Monitoring & Debugging
- Fast deployment
- Testable
- Granular

- No dependencies on monolith
- Cohesive and loosely coupled

### Architecture Patterns

- Solid Principles
  - Single Responsibility Principle
- Clean Architecture
- Command Query Responsibility Segregation
  - Event Sourcing
  - Sagas 😇

![event sourcing](https://codeopinion.com/wp-content/uploads/2021/12/1-3-2048x642.png)

#### Strangler Application

![fig strangler concept](https://martinfowler.com/bliki/images/stranglerApplication/11090068.jpg)

![how microservices ecosystem growths with strangler application](https://microservices.io/i/decompose-your-monolith-devnexus-feb-2020.001.jpeg)

> Thanks to **[Chris Richardson](https://microservices.io/)** and **[Martin Fowler](https://martinfowler.com/)** again!

#### DDD

> A domain-way application's decomposition by clean architecture

![clean architecture](https://cdn-media-1.freecodecamp.org/images/1*nEATDe5dRLIWN3MSxSjG0A.png)

> Domain is a core!

> Good for mid-size or big systems with complex business logic

- Ubiquitos Language
  - Terms
  - Places
    - User Stories
    - Code
- Sub-Domains & Bounded Context
- Value Objects
  - Immutable
  - Scalar & Lightweight
  - Reference or Structural Equality
- Entity
  - Identity
  - Rich Domain Models
  - Reference or Identity Equality
- Aggregate
  - Transactions
- Repositories
  - One Per Aggregate
  - DB, ORM
- Domain Events
  - Or not? Maybe GRPC

#### Anti Patterns

- Anemic Domain Models
  - Domain objects without behavior

- Fat Entities

- ~~Measure number of services~~

### Algorithm

> Make the most of the monolith

> Mind new features as separate services

> Success is improved velocity and reliability

> Return on Investment (ROI)

> Begin with the end in mind

- Understand Domain
  - Technical Application Overview
  - Model & Draw
- DevOps
  - Tests
- Choose a Service to Refactor
  - Edge case to proof CI/CD
  - High value services
- Refactor
  - Split code & database

## Summary

## Feedback

Please [share your feedback](https://forms.gle/8UcN6H1VaWtekCaPA) on our workshop. Thank you and have a great coding!

If you like the workshop, you can become our [patron](https://www.patreon.com/xtechnology), yay! 🙏

## Links

- [Bank Application](https://github.com/pietrzakadrian/bank-server) by [Adrian Pietrzak](https://twitter.com/PietrzakAdrian)
- [Melvin E. Conway's law, 1967](https://en.wikipedia.org/wiki/Conway%27s_law)
- [Monolith](https://microservices.io/patterns/monolithic.html)
- [Prereqiuisites and principles](https://martinfowler.com/bliki/MicroservicePrerequisites.html)
- [How to break a Monolith into Microservices](https://martinfowler.com/articles/break-monolith-into-microservices.html)

### Technologies

microservices
node.js
javascript
architecture
ddd
protobuf
grpc
typescript
turborepo
npm
yarn
docker
git
banking
