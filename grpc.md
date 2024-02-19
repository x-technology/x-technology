---
title: XTechnology Workshop - How to convert crypto currencies with GRPC microservices in Node.js
---

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

  img[alt*="photo"] {
    max-width: 250px !important;
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

# How to convert crypto currencies with GRPC microservices in Node.js

<div class="twitter-btn">
  <a href="https://twitter.com/XTechnology5/status/1513973177768157200"><i></i></a>
</div>

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

- [Workshop Event - January 29, 2022 10:00 AM CET](https://www.eventbrite.co.uk/e/how-to-convert-crypto-currencies-with-grpc-microservices-in-nodejs-tickets-254034322497?aff=private)
- [Repository](https://github.com/x-technology/mono-repo-nodejs-svc-sample)
- [Practical Exercises as Github Issues](https://github.com/x-technology/mono-repo-nodejs-svc-sample/issues)

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
- [Crypto 🦄 Currency Converter](#crypto-currency-converter)
  - [Prerequisites](#prerequisites-1)
  - [Monorepo structure](#monorepo-structure)
  - [Using Lerna](#using-lerna)
  - [Common & Services](#common--services)
  - [What we're building](#what-were-building)
  - [Deeper look into *.proto files](#deeper-look-into-proto-files)
  - [How to create new common lib](#how-to-create-new-common-lib)
  - [How to create new service](#how-to-create-new-service)
  - [How to test services](#how-to-test-services)
  - [How to run this magic](#how-to-run-this-magic-)
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

[![andrew reddikh](https://andrew.red/static/8ff3a66d3bd0a98ee9ed80636e94fc3d/65c8c/photo.avif)](https://andrew.red)

Software Engineer, United Kingdom

Passionate software engineer with expertise in software development, microservice architecture, and cloud infrastructure. On daily basis, I use Node.js, TypeScript, Golang, and DevOps best practices to build a better tech world by contributing to open source projects.

- [AndrewRedUK](https://twitter.com/AndrewRedUK)
- [mazahaca](https://github.com/mazahaca)

### What are we going to do today?

[⬆️ About](#how-to-convert-crypto-currencies-with-grpc-microservices-in-nodejs)

### Which technologies are we going to use?

[⬇️ Tags](#technologies)

### What is GRPC?

<a href="https://grpc.io/"><img src="https://github.com/grpc/grpc-community/blob/main/PanCakes/Pancakes_Bandana.png?raw=true" width="500px" alt="grpc logo aka pancakes"/></a>

<details><summary>gRPC Remote Procedure Calls, of course!</summary>

<img src="https://i.kym-cdn.com/photos/images/original/002/086/808/90f.gif" alt="obvious reaction"/>

</details>

> [gRPC](https://grpc.io/docs/what-is-grpc/faq/) is a *modern, open source* *remote procedure call (RPC)* framework that can run anywhere. It enables *client and server* applications to communicate transparently, and makes it easier to build connected systems

**History**

![microservices graph](https://github.com/x-technology/mono-repo-nodejs-svc-sample/raw/main/docs/assets/graph.png)

- March 2015 🗓
- Google ➡️ Open Source
<!-- > Why? If noone knows about it, it slows you down! -->
- Standardize Microservices Architecture, Framework & Infrastructure
  - `SPDY (HTTP/2)`
  - `QUIC (HTTP/3)`
  - `Stubby`
- Part of [Cloud Native Computing Foundation](https://www.cncf.io/projects/grpc/)
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

Questions
- How does a client service calls a remote service?
- How to expose a remote service?
- How data is serialized for network?
- How communication happens?
- Authentication?

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
<li><a href="https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events">Server-Sent Events</a></li>
</ul>
</details>

> We always need a **client** library to communicate to a server!

#### Features

![Architecture](https://grpc.io/img/landing-2.svg)

- Service Definitions (Protocol)
  - Strong Typed
  - Protocol Buffers ⏭
- Client & Server
  - Generated Code (Stubs)
  - [10+ Languages](https://grpc.io/docs/languages/)
  - [Platforms & Environments](https://grpc.io/docs/platforms/) - Android, Web, Flutter
  - [Core version 1.43.0](https://github.com/grpc/grpc)
  - Extension Points
- Communication
  - HTTP/2
  - Serialization
  - Message Ordering
  - Streams
  - Sync/Async
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
  // rule type name tag
  repeated uint64 vals = 4;
}
```

> Do you know what numbers on the right side mean?

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

```proto
// rule type name tag
repeated uint64 vals = 1;
```

- Fields & Types
  - Message
  - Scalar
  - Enums
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
- Required, **Optional**
- [No versioning](https://developers.google.com/protocol-buffers/docs/overview#updating)
  - Don't change tags for existing fields
  - `package mypackage.v1`, `package mypackage.v2beta1`
- Maps, oneOf, allOf

### [Demo](https://github.com/x-technology/mono-repo-nodejs-svc-sample/blob/main/docs/demo-protobuf/package.json#L5)

```json
// package.json
"scripts": {
  "1. download prices": "node index.js",
  "2. generate protobuf runtime": "protoc --js_out=import_style=commonjs,binary:. prices.proto",
  "3. run protobuf transformation": "node index.js",
  "4. start grpc server": "node grpc-server.js",
  "5. start grpc client": "node grpc-client.js"
}
```

#### Demo 1 - Use protobuf to serialize and store JSON

- `protoc` - [Protocol Buffer Compiler](https://grpc.io/docs/protoc-installation/)

```bash
protoc --js_out=import_style=commonjs,binary:. my.proto
# es6 not supported yet
```

- [`google-protobuf`](https://www.npmjs.com/package/google-protobuf) - protobuf runtime library
- [Bitcoin (historical data)](https://sampleapis.com/api-list/bitcoin)
- `vscode-proto3` extension

#### Demo 2 - Hello GRPC Node.js server & client

- How are we going to use Node.js?
  - [grpc](https://www.npmjs.com/package/grpc) ➡️ [@grpc/grpc-js](https://www.npmjs.com/package/@grpc/grpc-js)
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

- `java` client

### Q&A

- Why have we chosen TypeScript?
- Why lerna or yarn workspaces?
- Are we going to deploy?

## Crypto 🦄 Currency Converter

### Prerequisites

#### 1. Checkout demo project

Let's get started from cloning demo monorepo

```shell
git clone git@github.com:x-technology/mono-repo-nodejs-svc-sample.git
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
- `./package.json` - description of our package, containing the important part:
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

### Common & Services

Let's look into `./packages/common`. It contains common libraries used in other places of the system.
One of such libraries is `@common/grpc`, it contains proto generated into TypeScript/JavaScript formats as well as common
gRPC server.

Following command is required to be run if we're changing proto's:

```shell
cd ./packages/common/go-grpc && yarn build

# OR using lerna

yarn lerna run build --scope=@common/*
```

For this particular task we implement only gRPC services which are stored in the folder `./packages/services/grpc`. But if we decide to add `rest`, `./packages/common/rest` is a good place to add it.

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

### Deeper look into *.proto files

In the proto folder, according to our schema we created following files:
- `currency-converter.proto` - converter interface
- `currency-provider.proto` - provider interface
- `ecb-provider.proto` and `crypto-provider.proto` - implementation of two particular providers.

In implementation provider, we could just `import` an existing proto file and use its definitions.

```protobuf
import "currency-provider.proto";

package ecbProvider;

service EcbProvider {
  rpc GetRates(currencyProvider.GetRatesRequest) returns (currencyProvider.GetRatesResponse) {}
}
```

Let's take a deeper look of how proto's are generated from .proto to JavaScript.

Going back to `@common/go-grpc` module, we can find `./bin/build.mjs`.

Here is the main command we could find there:

```shell
protoc --plugin="protoc-gen-ts=`pwd`/node_modules/.bin/protoc-gen-ts" --ts_out="service=grpc-node:`pwd`/src/proto" --proto_path="`pwd`/../../../proto/" `pwd`/../../../proto/*.proto
```

### How to create new common lib

We use [hygen](https://www.hygen.io) for templating our new services and common libraries.

`1.` For example, we want to create a new `logger` library.
`2.` In the root directory run command `yarn bootstrap:common` and follow starter.
`3.` Go to the new folder in the terminal

```shell
cd ./packages/common/logger
```

`4.` Install dependencies

```shell
yarn install
```

`5.` Make sure to define appropriate name in the package.json file:

```json
"name": "@common/logger",
```

Let's follow a rule all common libraries have a prefix `@common/`

`6.` Create our library in a `src/index.js`

```shell
export const debug = (message: string) => console.debug(message);
export const info = (message: string) => console.info(message);
export const error = (message: string) => console.error(message);
export default { debug, info, error };
```

`7.` Make sure it builds successfully withing a command:

```shell
yarn build
```

`8.` Let's connect our newly created library somewhere in the existing service:

```shell
yarn lerna add @common/logger --scope=@grpc/ecb-provider
```

`9.` The final step, we need to use the library inside ecb-provider service. Let's amend file `./src/index.ts`:

```typescript
import logger from '@common/logger';

logger.debug('service has started');
```

`10.` Re-build ecb-provider to ensure there is no issues

```shell
yarn build
```

Yay! 🎉 It works!

### How to create new service

`1.` For example, we want to create a new `crypto-compare-provider` service, which is another currency rate provider returning cryptocurrencies.
`2.` Create a folder under `./packages/services/grpc/crypto-compare-provider` path. For simplicity, just copy an existing `ecb-provider` and rename it.
`3.` Go to the folder in the terminal

```shell
cd ./packages/services/grpc/crypto-compare-provider
```

`4.` Install dependencies

```shell
yarn install
```

`5.` Make sure to define appropriate name in the `package.json` file:

```json
"name": "@grpc/crypto-compare-provider",
```

Let's follow a rule - all grpc services have a prefix `@grpc/`.
`6.` Create a service method file `packages/services/grpc/crypto-provider/src/services/getRates.ts`

```shell
import { currencyProvider } from '@common/go-grpc';

export default async (
  _: currencyProvider.GetRatesRequest,
): Promise<currencyProvider.GetRatesResponse> => {
  return new currencyProvider.GetRatesResponse({
    rates: [],
    baseCurrency: 'USD',
  });
};
```

`7.` So next we need to use this method inside `server.ts`

```typescript
import { Server, LoadProtoOptions, currencyProvider } from '@common/go-grpc';
import getRates from './services/getRates';

const { PORT = 50051 } = process.env;
const protoOptions: LoadProtoOptions = {
  path: `${__dirname}/../../../../../proto/crypto-compare-provider.proto`,
  // this value should be equvalent to the one defined in *.proto file as "package cryptoCompareProvider;"
  package: 'cryptoCompareProvider',
  // this value should be equvalent to the one defined in *.proto file as "service CryptoCompareProvider"
  service: 'CryptoCompareProvider',
};

const server = new Server(`0.0.0.0:${PORT}`, protoOptions);
server
  .addService<currencyProvider.GetRatesRequest,
    Promise<currencyProvider.GetRatesResponse>>('GetRates', getRates);
export default server;
```

`8.` Make sure it builds successfully withing a command:

```shell
yarn build
```

`9.` Start the service with the command:

```shell
yarn start
```

Yay! 🎉 It works!

### How to test services

We use [jest](https://jestjs.io/docs/getting-started) as a test framework and decided to write integration tests for our services.
This is the best way to understand different situations, which could happen with services on the particular input/output.

`1.` Let's begin from creating a test file `test/services/index.spec.ts`

```shell
mkdir -p test/services
touch test/services/index.spec.ts
```

`2.` First of all in the test we need to define a server, which is imported from `src` folder and start it in the section `beforeAll`

```typescript
import { ecbProvider, currencyProvider, createInsecure } from '@common/go-grpc';
import server from '../../src/server';

const testServerHost = 'localhost:50061';
beforeAll(async () => {
   await server.start(testServerHost);
});
afterAll(async () => {
   await server.stop();
});
```

`3.` Next let's create a client which will invoke server's methods via gRPC protocol

```typescript
import { ecbProvider, createInsecure } from '@common/go-grpc';

const client = new ecbProvider.EcbProviderClient(
  testServerHost,
  createInsecure(),
);
```

`4.` Let's add first test suite in here and expect some particular result from the service's method

```typescript
describe('GetRates', () => {
 it('should return currency rates', async () => {
    const response = await client.GetRates(new currencyProvider.GetRatesRequest());

    expect(response.toObject()).toEqual({
      baseCurrency: 'EUR',
      rates: [
        { currency: 'USD', rate: 1.1348 },
      ],
    });
  });
});
```

`5.` Now it's time to try it out with a command:

```shell
yarn test
```

Brilliant! 🎉 It works!

### How to run this magic 🪄?

How could we run this magic to convert for us some currency?

```shell
export PORT=50052 && cd ./packages/services/grpc/ecb-provider/ && yarn start
export PORT=50051 && cd ./packages/services/grpc/currency-provider/ && yarn start
```

Here is a tool [grpcurl](https://github.com/fullstorydev/grpcurl#installation) for sending a test request to gRPC service from the terminal.

```shell
# list all services
grpcurl -import-path ./proto -proto ecb-provider.proto list

# list all methods of service
grpcurl -import-path ./proto -proto ecb-provider.proto list ecbProvider.EcbProvider

# call method GetRates
echo '{}' | grpcurl -plaintext -import-path ./proto -proto ecb-provider.proto -d @ 127.0.0.1:50052 ecbProvider.EcbProvider.GetRates
```

Hurray! 🚀

## Practice

It's time to have some practice and evolve our services even more!

Let's grab a task based on the things you'd like to do 👇

- [Issues](https://github.com/x-technology/mono-repo-nodejs-svc-sample/issues)

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
  <li>[More...](https://www.karanpratapsingh.com/courses/system-design/rest-graphql-grpc)</li>
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

Please [share your feedback](https://forms.gle/7jyTCxQBqata6SiX6) on our workshop. Thank you and have a great coding!

If you like the workshop, you can become our [patron](https://www.patreon.com/xtechnology), yay! 🙏

## Links

- [Protocol Buffers - Developers Google](https://developers.google.com/protocol-buffers)
- [gRPC](https://www.grpc.io/)
- [Scalable Microservices with gRPC, Kubernetes, and Docker by Sandeep Dinesh, Google](https://www.youtube.com/watch?v=xsIwYL-N4vI)
- [NestJS Microservices - 4 - Using gRPC](https://www.youtube.com/watch?v=OuyxRE9xLw4)
- [Getting Started with gRPC and JavaScript - Colin Ihrig, Joyent](https://www.youtube.com/watch?v=fl9AZieRUaw)
- [Protocol Buffers Crash Course](https://youtu.be/46O73On0gyI)
- [gRPC Crash Course - Modes, Examples, Pros & Cons and more](https://www.youtube.com/watch?v=Yw4rkaTc0f8)
- [A basic tutorial introduction to gRPC in Node](https://www.grpc.io/docs/languages/node/basics/)
- [Choosing An API Technology: GRPC, REST, GraphQL - Jura Gorohovsky](https://speedscale.com/2021/07/20/choosing-an-api-technology-grpc-rest-graphql/)
- [GraphQL, gRPC or REST? Resolving the API Developer's Dilemma - Rob Crowley](https://www.youtube.com/watch?v=l_P6m3JTyp0)
- [The Story of Why We Migrate to gRPC and How We Go About It - Matthias Grüter, Spotify](https://www.youtube.com/watch?v=fMq3IpPE3TU)
- [Introduction to gRPC: A general RPC framework that puts mobile and HTTP/2 first by Mete Atamel](https://www.youtube.com/watch?v=kUz2zjkKxFg)
- [GraphQL vs REST comparison](https://www.apollographql.com/blog/graphql/basics/graphql-vs-rest/)

### Technologies

microservices
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
