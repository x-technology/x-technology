[![XTechnology - Technology is beautiful, let's discover it together!](https://user-images.githubusercontent.com/1259644/139526072-c2df5b3f-86b3-40eb-a91a-e51a307269ec.png)](https://xtechnology.dev/)

<style type="text/css">
  img[alt="andrew reddikh"] {
    filter: grayscale(100%);
  }

  img[alt="microservices graph"] {
    width: 500px;
  }
</style>

# How to convert crypto currencies with GRPC microservices in Node.js

The workshop overviews key architecture principles, design patterns, and technologies used to build microservices in the Node.js stack. It covers the theory of the GRPC framework and protocol buffers mechanism, as well as techniques and specifics of building isolated services using the monorepo approach with lerna and yarn workspaces, TypeScript. The workshop includes a live practical assignment to create a currency converter application that follows microservices paradigms. It fits the best developers who want to learn and practice GRPC microservices pattern with the Node.js platform.

## General

- 3-4 hours
- Advanced level
- Technologies overview - GRPC, protocol buffers, Node.js, TypeScript, lerna & yarn workspaces
- Example structure - lerna configuration, packages configuration, common utilities, demo service
- Practical exercise - build a currency converter service

### Prerequisites

- Good understanding of JavaScript or TypeScript
- Experience with Node.js and writing Backend applications
- [Preinstall Node.js, npm](https://nodejs.org/en/download/)
- [Preinstall Protocol Buffer Compiler](https://grpc.io/docs/protoc-installation/)
- We prefer to use VSCode for a better experience with JavaScript and TypeScript (other IDEs are also ok)

### Instructors

[Alex Korzhikov](https://twitter.com/AlexKorzhikov) & [Andrew Reddikh](https://twitter.com/AndrewRedUK)

### Materials

[Register for Workshop - January 29, 2022 10:00 AM CET](https://www.eventbrite.co.uk/e/how-to-convert-crypto-currencies-with-grpc-microservices-in-nodejs-tickets-254034322497?aff=telegram)
[Repository](https://github.com/x-technology/mono-repo-nodejs-svc-sample)

![repository-open-graph-template 1](https://user-images.githubusercontent.com/1259644/115153860-493a2880-a078-11eb-85c8-201b1512ee4b.png)

# Workshop Begins!

## Agenda

- [Introduction](#introduction)
  - [Who are we?](#who-are-we)
  - [What are we going to do today?](#how-to-convert-crypto-currencies-with-grpc-microservices-in-nodejs)
  - [Which technologies are we going to use?](#technologies)
  - [What is GRPC?](#what-is-grpc)
  - [What are Protocol Buffers?](#what-are-protocol-buffers)
  - [Demo](#demo)
  - [Q&A](#qa)
- [Example](#example)
  - Structure
  - Common
  - GRPC Web Service Wrapper
  - Local Setup
- Practice
  - Demo
- Summary

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

[⬆️ About](#how-to-convert-crypto-currencies-with-grpc-microservices-in-nodejs)

### Which technologies are we going to use?

[⬇️ Tags](#technologies)

### What is GRPC?

<details><summary>gRPC Remote Procedure Calls, of course!</summary>

<img src="https://i.kym-cdn.com/photos/images/original/002/086/808/90f.gif" alt="obvious reaction"/>

</details>

> [gRPC](https://grpc.io/docs/what-is-grpc/faq/) is a *modern, open source* *remote procedure call (RPC)* framework that can run anywhere. It enables *client and server* applications to communicate transparently, and makes it easier to build connected systems

**History**

![microservices graph](https://github.com/x-technology/mono-repo-nodejs-svc-sample/raw/main/docs/assets/graph.png)

- March 2015 🗓
- Google ➡️ Open Source 
- Standardize Microservices Architecture, Framework & Infrastructure
  - Stubby
  - SPDY
  - QUIC
- [Motivation](https://grpc.io/blog/principles/), FAQ, Tutorials

**RPC**

A *distributed computing technique* when

- A client program sends a request to a known remote server to execute a specified procedure
- The remote server executes local procedure and sends a response back to the client
- The client continues to run

More steps involved in the process
- local client stub
- marshalling parameters into a message
- remote server call
- local server stub
- unpacking or unmarshalling message parameters

**Client 😀 ⬅️ ➡️ 💻 Server Communication**

<details><summary>Web Protocols</summary>
<ul>
<li>SOAP</li>
<li>REST</li>
<li>GraphQL</li>
</ul>
Or even more generic
<ul>
<li>HTTP/1.1</li>
<li>HTTP/2</li>
<li>TCP</li>
<li>UDP</li>
<li>WebSockets</li>
</ul>
</details>

> We always need a **client** library to communicate to a server!

#### Features

![Architecture](https://grpc.io/img/landing-2.svg)

- Client & Server
  - Generated Code (Stubs)
  - [10+ Languages](https://grpc.io/docs/languages/)
  - [Platforms & Environments](https://grpc.io/docs/platforms/) - Android, Web, Flutter
  - [Core version 1.43.0](https://github.com/grpc/grpc)
- Communication
  - HTTP/2
  - Message Ordering
  - Streams

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

  - Sync/Async
  - Authentication
- Protocol - Service Definitions
  - Typed
  - Protocol Buffers ⏭

### What are Protocol Buffers?

*An efficient technology to serialize structured data*

```proto
message Person {
  string name = 1;
  int32 id = 2;
  bool has_ponycopter = 3;
}
```

> Does anyone know what numbers on the right side mean?

**History**

- [Protocol Buffers - Google Developers](https://developers.google.com/protocol-buffers/)
- [July 2008](https://github.com/protocolbuffers/protobuf/commit/40ee551715c3a784ea6132dbf604b0e665ca2def) 🗓
- Google ➡️ Open Source

**Features**

- Typed `.proto` format
- Code Generation
  - `protoc` - the protocol buffers compiler
  - [10+ Languages](https://github.com/protocolbuffers/protobuf#protobuf-runtime-installation)
  - [Third-Party Add-ons for Protocol Buffers](https://github.com/protocolbuffers/protobuf/blob/master/docs/third_party.md)
- Services Description

**Advanced**

- Types
  - Message
  - Scalar
  - Enums
  - Required, Optional
  - Repeated
  - No void type, no scalar types in arguments
- Packages
- Services - not used by `protobuf` directly

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

- Plugins
- Compiler Options
- Nested Types
- [No versioning](https://developers.google.com/protocol-buffers/docs/overview#updating)
- Maps, oneOf, allOf

### Demo

#### Demo 1 - Use protobuf to serialize and store JSON

- `protoc` - [Protocol Buffer Compiler](https://grpc.io/docs/protoc-installation/)

```bash
protoc --js_out=import_style=commonjs,binary:. my.proto
```

- [`google-protobuf`](https://www.npmjs.com/package/google-protobuf) - protobuf runtime library
- [Bitcoin (historical data)](https://sampleapis.com/api-list/bitcoin)
- `vscode-proto3` extension

#### Demo 2 - Hello GRPC Node.js server & client

- How are we going to use Node.js?
  - [grpc](https://www.npmjs.com/package/grpc) -> [@grpc/grpc-js](https://www.npmjs.com/package/@grpc/grpc-js)
  - [protobuf.js](https://www.npmjs.com/package/protobufjs) + [@grpc/proto-loader](https://www.npmjs.com/package/@grpc/proto-loader)
  - [Dynamic](https://github.com/grpc/grpc/tree/v1.42.0/examples/node/dynamic_codegen/route_guide) VS [Static](https://github.com/grpc/grpc/tree/v1.42.0/examples/node/static_codegen/route_guide)
  - [Streams](https://nodejs.org/dist/latest-v16.x/docs/api/stream.html)

```js
// https://www.npmjs.com/package/@grpc/proto-loader#usage
const protoLoader = require('@grpc/proto-loader');
const grpcLibrary = require('grpc');
// OR
const grpcLibrary = require('@grpc/grpc-js');

protoLoader.load(protoFileName, options).then(packageDefinition => {
  const packageObject = grpcLibrary.loadPackageDefinition(packageDefinition);
});
// OR
const packageDefinition = protoLoader.loadSync(protoFileName, options);
const packageObject = grpcLibrary.loadPackageDefinition(packageDefinition);
```

### Q&A

- Why have we chosen TypeScript?
- Why lerna or yarn workspaces?
- Are we going to deploy?

## Example

- Structure
- Common
- GRPC Web Service Wrapper
- Local Setup

## Practice

- Task
- Demo

## Summary

<details><summary>Why?</summary>
<ul>
  <li>Yet Another Standard</li>
  <li>Environment, Language Agnostic</li>
  <li>Strongly Typed Messaging</li>
  <li>Efficient, Compact Data Format</li>
  <li>Fast & Efficient Transport Protocol (streams, cancelation)</li>
  <li>Compiler Support by Community and Key Organisations (single client)</li>
  <li>Security</li>
  <li>Scalable</li>
  <li>Free & Open</li>
  <li>Pluggable</li>
  <li>Layered</li>
</ul>
</details>
  
<details><summary>What are the GRPC alternatives?</summary>
<ul>
  <li>REST("JSON"-ish over HTTP)</li>
  <li>GraphQL</li>
</ul>
<table>
    <tr>
        <td>Compare</td>
        <td>REST</td>
        <td>RPC</td>
        <td>GraphQL</td>
    </tr>
    <tr>
        <td>Focus</td>
        <td>Resource</td>
        <td>Action</td>
        <td>Resource</td>
    </tr>
    <tr>
        <td>Semantics</td>
        <td>HTTP</td>
        <td>Programming</td>
        <td>Programming</td>
    </tr>
    <tr>
        <td>Coupling</td>
        <td>Loose</td>
        <td>Tighter</td>
        <td>Loose</td>
    </tr>
    <tr>
        <td>Format</td>
        <td>Text</td>
        <td>Binary</td>
        <td>Text</td>
    </tr>
</table>
</details>

## Feedback

# Links

- [Protocol Buffers - Developers Google](https://developers.google.com/protocol-buffers)
- [gRPC](https://www.grpc.io/)
- [Scalable Microservices with gRPC, Kubernetes, and Docker by Sandeep Dinesh, Google](https://www.youtube.com/watch?v=xsIwYL-N4vI)
- [NestJS Microservices - 4 - Using gRPC](https://www.youtube.com/watch?v=OuyxRE9xLw4)
- [Getting Started with gRPC and JavaScript - Colin Ihrig, Joyent](https://www.youtube.com/watch?v=fl9AZieRUaw)
- [Protocol Buffers Crash Course](https://youtu.be/46O73On0gyI)
- [gRPC Crash Course - Modes, Examples, Pros & Cons and more](https://www.youtube.com/watch?v=Yw4rkaTc0f8)
- [A basic tutorial introduction to gRPC in Node](https://www.grpc.io/docs/languages/node/basics/)
- [Choosing An API Technology: GRPC, REST, GraphQL - Jura Gorohovsky](https://speedscale.com/2021/07/20/choosing-an-api-technology-grpc-rest-graphql/)

### Technologies

- microservices
- node.js
- javascript
- protobuf
- grpc
- typescript
- lerna
- npm
- yarn
- docker
- git
- architecture
- crypto
- currency
