[![XTechnology - Technology is beautiful, let's discover it together!](https://user-images.githubusercontent.com/1259644/139526072-c2df5b3f-86b3-40eb-a91a-e51a307269ec.png)](https://xtechnology.dev/)

<style type="text/css">
  h1:first-child {
    display: none;
  }
  
  img[alt="andrew reddikh"] {
    filter: grayscale(100%);
  }

  img[alt="microservices graph"] {
    width: 500px;
  }
</style>

# How to develop, build, and deploy Node.js microservices with Pulumi and Azure DevOps

The workshop gives a practical perspective of key principles needed to develop, build, and maintain a set of microservices in the Node.js stack. It covers specifics of creating isolated `TypeScript` dockerized services using the monorepo approach with **lerna and yarn** workspaces. The workshop includes an overview and a live exercise to create cloud environment with **Pulumi** framework and **Azure** services. The sessions fits the best developers who want to learn and practice build and deploy techniques using Azure stack and Pulumi, Docker for Node.js.

## General

- 3-4 hours
- Advanced level
- Technologies overview - Pulumi, Azure DevOps, Docker, Kubernetes, Node.js, TypeScript, lerna & yarn workspaces
- Example structure - lerna configuration, common utilities, demo services
- Practical exercise - create cloud environment and deploy microservices to cluster

### Prerequisites

- Good understanding of JavaScript or TypeScript
- Experience with Node.js and writing Backend applications
- [Preinstall Node.js, npm](https://nodejs.org/en/download/)
- [Preinstall Docker](https://docs.docker.com/get-docker/), [docker-compose](https://docs.docker.com/compose/install/)
- [Preinstall Protocol Buffer Compiler](https://grpc.io/docs/protoc-installation/)
- We prefer to use VSCode for a better experience with JavaScript and TypeScript (other IDEs are also ok)
- [Register in Microsoft](https://azure.microsoft.com/en-us/pricing/purchase-options/pay-as-you-go/) to repeat all the Azure steps
- [Preinsall Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli) to manage Azure resources

### Instructors

[Alex Korzhikov](https://twitter.com/AlexKorzhikov) & [Andrew Reddikh](https://twitter.com/AndrewRedUK)

### Materials

- [Workshop Event - April 2, 2022 10:00 AM CET](https://www.eventbrite.com/e/deploy-nodejs-microservices-with-pulumi-and-azure-devops-tickets-308874149897)
- [Repository](https://github.com/x-technology/micro-services-infrastructure-pulumi-azure-devops/)
- [Practical Exercises as Github Issues](https://github.com/x-technology/micro-services-infrastructure-pulumi-azure-devops/issues)
- [Recording](https://www.youtube.com/watch?v=exuHhQiAqrs&t=3185s)

![repository-open-graph-template 1](https://user-images.githubusercontent.com/1259644/115153860-493a2880-a078-11eb-85c8-201b1512ee4b.png)

# Workshop Begins!

## Agenda

- [Introduction](#introduction)
  - [Who are we?](#who-are-we)
  - [What are we going to do today?](#how-to-develop-build-and-deploy-nodejs-microservices-with-pulumi-and-azure-devops)
  - [Which technologies are we going to use?](#technologies)
- [Crypto 🦄 Currency Converter - Node.js](#crypto-currency-converter)
  - [What we're building](#what-were-building)
  - [Prerequisites](#prerequisites)
  - [Monorepo structure](#monorepo-structure)
  - [Using Lerna](#using-lerna)
  - [What is GRPC?](#what-is-grpc)
  - [What are Protocol Buffers?](#what-are-protocol-buffers)
  - [Demo - Run Microservices Locally](#demo---run-microservices-locally)
- [Build Microservices - Docker](#build-microservices---docker)
  - [Docker](#docker) - [Dockerfile](#dockerfile), [docker-compose](#docker---compose)
- [Infrastructure - Azure](#infrastructure---azure)
  - [Introduction to Azure](#introduction-to-azure)
  - [Pulumi](TODO)
  - [Make Kubernetes Cluster](TODO)
  - [Azure Deploy](TODO)
- [Deploy Microservices - Pulumi](TODO)
  - [Pulumi Docker Images](TODO)
  - [Helm](TODO)
- [Practice](#practice)
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

[⬆️ About](#how-to-develop-build-and-deploy-nodejs-microservices-with-pulumi-and-azure-devops)

### Which technologies are we going to use?

[⬇️ Tags](#technologies)

## Crypto 🦄 Currency Converter - Node.js

### What we're building

We're building a currency converter, which can be used over gRPC calls.

![currency convertor schema](https://github.com/x-technology/mono-repo-nodejs-svc-sample/raw/main/docs/demo/currency-convertor-schema.png)

Our intention is to send a request similar to `convert 0.345 ETH to CAD` and as a result we want to know the final amount in CAD and conversion rate.
We also assume that, it could be more than one currency provider, e.g.
1. Europe Central Bank rates
2. Bank of England rates
3. Crypto Rates

Here is how it works:
- **Currency Converter** fetches each of the provider, accumulates, and uses for conversion rates received from providers.
- **Currency Provider** is a proxy to gain single source of rates, it also converts rates into the common format defined in proto's.

### Prerequisites

#### 1. Checkout demo project

Let's get started from cloning demo monorepo

```shell
git clone git@github.com:x-technology/micro-services-infrastructure-pulumi-azure-devops.git
```

#### 2. Install protoc

For efficient work with `.proto` format, and to be able to generate TypeScript-based representation of protocol buffers we need to install `protoc` library.

If you're a **MacOS user** and have [brew](https://brew.sh) package manager, the following command is the easiest way for installation:
```shell
brew install protobuf
# Ensure it's installed and the compiler version at least 3+
protoc --version
```

**For Linux users**

Run the following commands:

```shell
PROTOC_ZIP=protoc-3.14.0-linux-x86_64.zip
curl -OL https://github.com/protocolbuffers/protobuf/releases/download/v3.14.0/$PROTOC_ZIP
sudo unzip -o $PROTOC_ZIP -d /usr/local bin/protoc
sudo unzip -o $PROTOC_ZIP -d /usr/local 'include/*'
rm -f $PROTOC_ZIP
```

Alternately, manually download and install protoc from [here](https://github.com/protocolbuffers/protobuf/releases/download/v3.14.0/protoc-3.14.0-linux-x86_64.zip).

#### 3. Prepare environment

Make sure we have Node.js v14+ installed. If not, [nvm](https://github.com/nvm-sh/nvm#installing-and-updating) is a very good tool to install multiple node versions locally and easily switch between them.

Then we need to install dependencies and bootstrap lerna within the monorepo.

```shell
yarn install
yarn lerna bootstrap
```

Yay! 🎉 Now we're ready to go with the project.


### Monorepo structure

For better monorepo project management we used [Lerna](https://github.com/lerna/lerna) & [Yarn Workspaces](https://classic.yarnpkg.com/lang/en/docs/workspaces/)

The project shapes into the following structure:

![project structure](https://github.com/x-technology/mono-repo-nodejs-svc-sample/raw/main/docs/demo/project-structure.png)

- `./packages/common` folder contains common libraries used in other project's services.
- `./packages/services/grpc` folder contains gRPC services we build to share the product.
- `./proto` folder contains proto files, which describe protocol of input/output and communication between the services.
- `./node_modules` - folder with dependencies, shared between all microservices.
- `./lerna.json` - lerna's configuration file, defining how it should work with monorepo.
- `./package.json` - description of our package, containing the important part

```json
  "workspaces": [
    "packages/common/*",
    "packages/services/grpc/*"
  ]
```

Let's move on 🚚

### Using Lerna

Lerna brings to the table few commands which can be easily executed across all/or filtered packages.

We use our common modules compiled to JavaScript, so before using it in services we need to build it first.

Following command executed `build` command against all common packages filtered with flag `--scope=@common/*`
```shell
yarn lerna run build --scope=@common/*
```

### What is GRPC?

<a href="https://grpc.io/"><img src="https://github.com/grpc/grpc-community/blob/main/PanCakes/Pancakes_Bandana.png?raw=true" width="500px" alt="grpc logo aka pancakes"/></a>

<details><summary>gRPC Remote Procedure Calls, of course!</summary>

<img src="https://i.kym-cdn.com/photos/images/original/002/086/808/90f.gif" alt="obvious reaction"/>

</details>

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

### Demo - [Run Microservices Locally](https://github.com/x-technology/micro-services-infrastructure-pulumi-azure-devops)

```bash
npm start
```

```js
const all = require('@common/go-grpc')
const client = new all.ecbProvider.EcbProviderClient('0.0.0.0:50051', all.createInsecure());
const response = await client.GetRates(new all.currencyProvider.GetRatesRequest())
response.toObject()
```

```js
// inside converter container
const all = require('@common/go-grpc')
const client = new all.currencyConverter.CurrencyConverterClient('0.0.0.0:50052', all.createInsecure());
const response = await client.Convert(new all.currencyConverter.ConvertRequest({ sellAmount: 100, sellCurrency: 'USD', buyCurrency: 'GBP' }));
response.toObject()
```

## Build Microservices - Docker

![Docker Logo](https://www.docker.com/wp-content/uploads/2022/03/horizontal-logo-monochromatic-white.png)

### Docker

*Toolset to develop, declare, deliver and run applications*

```bash
docker version
docker run hello-world
```

- Image - a declared application and dependencies snapshot
- Container - created from an image, runs the application

![Linux Containers (LXC)](https://en.wikipedia.org/wiki/LXC#/media/File:Linux_Containers_logo.png)

*Powered by [Linux Containers](https://en.wikipedia.org/wiki/LXC)* - virtualization method to run multiple isolated Linux systems (containers) on a control host

- `cgroups` - limitation and prioritization of CPU, memory, block I/O, network resources
- `namespace` - isolated process trees, networking, users and file systems

**Features**

![Docker Running Services Diagram](https://docs.docker.com/engine/images/architecture.svg)

- Daemon - background service creating, running and destroying containers
- Client - CLI program to request and command resources
- Registry - database of published images
- Desktop - UI resources dashboard
- Kubernetes, `docker-compose`...

**Dockerfile**

*Instructions to declare an application*

- Cache Layers
- Build to Image

- `FROM` base image
- `RUN` install assets and dependencies
- `CMD` to start
- `COPY` to copy

**Lifecycle**

```bash
docker build -t tmp-base1 . # build image from Dockerfile
docker run hello-world # create a container from image
# docker run = docker create + docker start
# docker run -it tmp-base2:latest bash
docker ps # --all - list of running containers
docker kill # also stop
docker system prune
docker logs
# step into running container
docker exec -it $DOCKER_CONTAINER_HASH /bin/sh
# also ports, mount -v
```

### [docker-compose](https://github.com/docker/awesome-compose/tree/master/nginx-nodejs-redis)

*To start all components at once in configured network*

- `docker-compose` up

```yaml
# docker-compose.yaml
redis:
  image: 'redislabs/redismod'
  ports:
    - '6379:6379'
web1:
  restart: on-failure
  build: ./web
  hostname: web1
  ports:
    - '81:5000'
web2:
  restart: on-failure
  build: ./web
  hostname: web2
  ports:
    - '82:5000'
nginx:
  build: ./nginx
  ports:
  - '80:80'
  depends_on:
  - web1
  - web2
```

### Q&A

- What would happen when run `docker run ... echo hello` command?
- What's wrong with my `Dockerfile`?

```Dockerfile
COPY package.json yarn.lock /usr/src/main

# Install runtime dependencies
RUN yarn install

COPY . /usr/src/main
```

- Does anyone know why yarn is preinstalled in `node:lts-alpine`?
- What are the advantages of Infrastructure as a Code?

## Infrastructure - Azure

### Introduction to Azure

*`Microsoft Azure` is a enourmous cloud ecosystem that enables to organize, develop, publish applications worldwide*

- Organization Resources - Users, Tasks
- CI/CD - Repositories, Pipelines, Artifacts
- Integrations

### Demo - [Migrate to Azure](https://dev.azure.com/xtechnology5/_git/XTechnology)

- Azure DevOps
  - Repository
- [Azure Container Registry](https://portal.azure.com/#@hellole.onmicrosoft.com/resource/subscriptions/8706d28d-203d-4127-ac6e-2ab12c9caf33/resourcegroups/xtechnology-microservices/providers/Microsoft.ContainerRegistry/registries/xtechnology/quickStart)

```bash
docker login xtechnology.azurecr.io
docker image tag tmp-base2:latest xtechnology.azurecr.io/microservices-united:latest
docker push xtechnology.azurecr.io/microservices-united:latest
```

- [Azure Pipelines](https://dev.azure.com/xtechnology5/XTechnology/_apps/hub/ms.vss-build-web.ci-designer-hub)
  - [Service Connections](https://dev.azure.com/xtechnology5/XTechnology/_settings/adminservices)
  - [Build and Push](https://dev.azure.com/xtechnology5/XTechnology/_build?definitionId=1&_a=summary)

### Pulumi
### Make Kubernetes Cluster
### Azure Deploy

## Deploy Microservices - Pulumi
### Pulumi Docker Images
### Helm

## Practice

It's time to have some practice and evolve our services even more!

Let's grab a task based on the things you'd like to do 👇

- [Issues](https://github.com/x-technology/micro-services-infrastructure-pulumi-azure-devops/issues)

## Summary


- Azure
- Pulumi
  - Compare to Terraform

## Feedback

Please [share your feedback](https://forms.gle/8UcN6H1VaWtekCaPA) on our workshop. Thank you and have a great coding!

If you like the workshop, you can become our [patron](https://www.patreon.com/xtechnology), yay! 🙏

## Links

- [Docker Docs](https://docs.docker.com/)
- [Awesome Docker Compose](https://github.com/docker/awesome-compose)
- [Protocol Buffers Crash Course](https://youtu.be/46O73On0gyI)
- [gRPC Crash Course - Modes, Examples, Pros & Cons and more](https://www.youtube.com/watch?v=Yw4rkaTc0f8)

### Technologies

microservices
pulumi
azure
devops
node.js
javascript
protobuf
grpc
typescript
lerna
npm
yarn
docker
git
architecture
crypto
currency
