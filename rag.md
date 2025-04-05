---
title: XTechnology Workshop - Building a RAG System in Node.js: Vector Databases, Embeddings & Chunking
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

  img[alt*="photo"] {
    max-width: 250px !important;
  }
</style>

<div class="twitter-btn">
  <a href="https://twitter.com/XTechnology5/status/1662440871936114688"><i></i></a>
</div>

# Building a RAG System in Node.js: Vector Databases, Embeddings & Chunking

Large Language Models (LLMs) are powerful, but they often lack real-time knowledge. Retrieval-Augmented Generation (RAG) bridges this gap by fetching relevant information from external sources before generating responses. In this workshop, we’ll explore how to build an efficient RAG pipeline in Node.js using RSS feeds as a data source. We’ll compare different vector databases (FAISS, pgvector, Elasticsearch), embedding methods, and testing strategies. We’ll also cover the crucial role of chunking—splitting and structuring data effectively for better retrieval performance.

## Prerequisites

- Good understanding of JavaScript or TypeScript
- Experience with Node.js and API development
- Basic knowledge of databases and LLMs is helpful but not required

## Code

- [RAG Workshop](https://github.com/x-technology/rag-workshop)

## Agenda

- [Introduction 📢](#introduction)
- [About Everything](#about-everything)

## Introduction

### Alex Korzhikov

![alex korzhikov photo](https://github.com/x-technology/PizzaScript/blob/main/assets/alex-black-white-open-source.png?raw=true)

Software Engineer, Netherlands

My primary interest is self development and craftsmanship. I enjoy exploring technologies, coding open source and enterprise projects, teaching, speaking and writing about programming - JavaScript, Node.js, TypeScript, Go, Java, Docker, Kubernetes, JSON Schema, DevOps, Web Components, Algorithms 👋 ⚽️ 🧑‍💻 🎧

- [AlexKorzhikov](https://twitter.com/AlexKorzhikov)
- [korzio](https://github.com/korzio)

### Pavlik Kiselev

![Pavlik](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/team/pavlik.jpg?raw=true)

Software Engineer, Netherlands

JavaScript developer with full-stack experience and frontend passion. He runs a small development agency [codeville.agency](https://codeville.agency/) and likes to talk about technologies they use: React, Remix and Serverless.

- [Pavlik Kiselev](https://www.linkedin.com/in/pavlik-kiselev-06993347/)
- [paulcodiny](https://github.com/paulcodiny)

## About Everything

- Generative Artificial Intelligence (GenAI)

Use of Artificial Intelligence to produce human consumable content in **text**, image, audio, video format.

- Language Model (LM)

Language Models are Machine Learning models trained on natural language resources and aim predict next word based on given context.

LM relevant tasks - summarization, Q&A, classification, and more.

- Large Language Model (LLM)

Artificial Intelligence is powered by Large Language Models - models trained on tons of sources and materials, having billions of parameters.

![llm as blackbox](assets/llm-blackbox.png)

- Retrieval Augmented Generation (RAG)

RAG is a method that combines information retrieval with language model generation.

![alt text](assets/rag.png)

Retrieval = Search

Generation = LLM

Use Cases:
- Chat with user
- Analyze and summarise documents

```js
async function rag(q) {
  const results = await search(q)
  const prompt = makePrompt(q, results)
  const answer = await llm(prompt)
  return answer
}
```

Questions:
<details><summary>Why do we need RAG?</summary>
- Additional, specific knowledge<br>
- Reduce hallucinations<br>
- Control system costs<br>
</details>

<details><summary>What do we need to build a RAG?</summary>
- Application (backend)<br>
- Search system (vector databases)<br>
- LLM (blackbox)<br>
</details>

<details><summary>Why can't we just put all context in our LLM and ask it about?</summary>
- Cost<br>
- Slow<br>
- Size<br>
- Noize<br>
</details>

- Langchain 🦜️🔗

LangChain is a Python and JavaScript framework that brings flexible abstractions and AI-first toolkit for developers to build with GenAI and integrate your applications with LLMs. It includes components for abstracting and chaining LLM prompts, configure and use vector databases (for semantic search), document loaders and splitters (to analyze documents and learn from them), output parsers, and more.

## Setup

- Node.js
- Ollama / OpenAI
- `npm i langchain`

## Summary

## Feedback

Please [share your feedback](https://app.sli.do/event/wV641HGAr8jeVnULeLAAg2) on the workshop. Thank you and have a great coding!

<iframe src="https://wall.sli.do/event/wV641HGAr8jeVnULeLAAg2/?section=fdc6bb93-244d-4320-ac2d-cd6a3ffd6a38" width="50%" height="400px"></iframe>

If you like the workshop, you can become our [patron](https://www.patreon.com/xtechnology), yay! 🙏

## Links

- [Mete Atamel - A blog about software development and more](https://atamel.dev/)
- [Build a Retrieval Augmented Generation (RAG) App](https://js.langchain.com/docs/tutorials/rag/)
- [5 Levels Of Text Splitting](https://github.com/FullStackRetrieval-com/RetrievalTutorials/blob/main/tutorials/LevelsOfTextSplitting/5_Levels_Of_Text_Splitting.ipynb)
- [LlamaIndex - End-to-end tooling to ship a context-augmented AI agent to production](https://llama-playground.vercel.app/)
- [Ragas - ultimate toolkit for evaluating and optimizing Large Language Model (LLM) applications.](https://github.com/explodinggradients/ragas)
- [deepeval - the open-source LLM evaluation framework](https://docs.confident-ai.com/)
- [LLM Zoomcamp: A Free Course on Real-Life Applications of LLMs](https://github.com/DataTalksClub/llm-zoomcamp)

### Technologies

- LLM
- Langchain

## WIP

- [x] Which LLM? OpenAI? preinstall **Ollama**? huggingface

### 2025-03-30

- [x] @pavlik relevant documents to current processing article
  > which articles are relevant to current one

### 2025-03-25

- [ ] @alex embedding
- [ ] @pavlik alternative with ollama, in-memory store

### 2025-03-23

- [x] dry runs in ING/XT?

### 2025-03-18

- [x] @pavlik to build use case
- [x] @alex to prepare theory - how to split documents

### Agenda

- Introduction 📢 / 5 min / @alex @pavlik
- About Everything (theory) / 10 min / @alex
  - Generative AI
    - LLMs
      - LM
        > predict next word based on what you have typed so far
      - LLM trained on tons of materials, millions of parameters
      - black box (prompt -> LLM -> answer)
    - RAG
      Retrieval Augmented Generation
      Retrieval = Search
      Generation = LLM
      > Why can't we just put all context in our LLM and ask it about?
      > Why do we need RAG?
       - more context given
      - [ ] IMAGE: User Query -> DB KBs -> Found items -> Context to LLM -> answer
      > What to use?
        - DBs, LLMs
    - Langchain
      - Also, Langgraph & Langsmith
  - Vector Databases
  - Langchain
- Setup / 2 min / @pavlik
  - Node.js
  - Ollama / OpenAI
    - Options: OpenAI? preinstall Ollama? huggingface
  - `npm i langchain`
- Practical Examples / 10 min / @pavlik
  - First call to LLM
    > openai api quickly explained, how to create/use token?
  - Chat?
  - Langchain?
- Use Case - Retrieve and Parse RSS Documents, Organize with DB, Query, LLM
  - How to get documents / 5 min / @alex
    - prepared json, csv
    - [ ] naive implementation (search, prompt, llm)
  - How to split documents / 15 min / @alex
    > Chunking involves breaking down texts into smaller, manageable pieces called “chunks.” Each chunk becomes a unit of information that is vectorized and stored in a database, fundamentally shaping the efficiency and effectiveness of natural language processing tasks. Chunking is central to several aspects of RAG systems.

    [![text splitter](https://python.langchain.com/assets/images/text_splitters-7961ccc13e05e2fd7f7f58048e082f47.png)](https://python.langchain.com/docs/concepts/text_splitters/)

    [text splitter online example](https://chunkviz.up.railway.app/)
    [text splitter online example 2](https://textsplittervisualizer.com/)

    ![text splitter example](assets/text-splitter-online.png)

    <video width="50%" height="400px" controls>
      <source src="https://framerusercontent.com/assets/Syj9M1soD3kB2EvO4GeoATDATI.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>

    - Prepare
      - what dataset you have?
        - pdf docs, tables, code base, images in text?
      - what are search queries for your business use case?
        - types of retrieval queries?
      - How to test it upfront, TDD?
        - [Evaluate a simple LLM application](https://docs.ragas.io/en/latest/concepts/metrics/available_metrics/)
        - [unit test LLM outputs](https://docs.confident-ai.com/docs/evaluation-test-cases)
        - [Langsmith?](https://docs.smith.langchain.com/evaluation/tutorials/rag)
        - Metrics:
          - chunk attributions/utilization - if chunk contributed to model/rag response
      - Considerations:
        - DB size based on chunking methods. So, latency
        - LLM usage/price
        - embedding model size/llm context
    - Why?
      - normalize documents
      - model limitations: Many embedding models and language models have maximum input size constraints.
      - representation quality: For longer documents, the quality of embeddings or other representations may degrade as they try to capture too much information.
      - Enhancing retrieval precision: In information retrieval systems, splitting can improve the granularity of search results, allowing for more precise matching of queries to relevant document sections.
      - Optimizing computational resources: Working with smaller chunks of text can be more memory-efficient and allow for better parallelization of processing tasks.
    - What?
      - Chunk Size - The number of characters you would like in your chunks. 50, 100, 100,000, etc.
      - Chunk Overlap - The amount you would like your sequential chunks to overlap. This is to try to avoid cutting a single piece of context into multiple pieces. This will create duplicate data across chunks.
      - Chunks as **Documents**, also for other strategies
    - How? Strategies
      - Length-based (`CharacterTextSplitter`)
        - Character/Token splitters
        ```js
        import { CharacterTextSplitter } from "@langchain/textsplitters";
        const textSplitter = new CharacterTextSplitter({
          chunkSize: 100,
          chunkOverlap: 0,
        });
        const texts = await textSplitter.splitText(document);
        ```
        - Pros: Easy & Simple
        - Cons: Very rigid and doesn't take into account the structure of your text
      - Text-structured based (`RecursiveCharacterTextSplitter`)
        > What split characters do you think [are included](https://github.com/langchain-ai/langchain/blob/9ef2feb6747f5a69d186bd623b569ad722829a5e/libs/langchain/langchain/text_splitter.py#L842) in Langchain by default?
      - Document-structured based
        - [Code splitters](https://python.langchain.com/docs/how_to/code_splitter/)
        > [more separators](https://github.com/langchain-ai/langchain/blob/9ef2feb6747f5a69d186bd623b569ad722829a5e/libs/langchain/langchain/text_splitter.py#L983)
      - Semantic meaning based
        - Heirarchical clustering with positional reward?
        - break points between sequential sentences
        - NLP?
          - [text into propositions](https://chentong0.github.io/factoid-wiki/) (facts)
          - spacy/ntlk?
        - Cons: complexity
      - More / Agentic Chunking
        - [multiple embeddings](https://js.langchain.com/docs/how_to/multi_vector/)
        - Cons: expensive, LLM dependent
        - LM approach?
          - summarize images in text
        - Summarize documents/chunks?
          - propositions (again)
        - store documents as hypothetical Questions
          - chat messages
    - practice / @pavlik
      > try different splitters
  - How to store & retrieve / 30 min / @alex
    - Embeddings
      > embed or not?
      - decrease vector dimension compare to traditional text indexing
      > How to choose embeddings?
      metrics:
        - relevant documents
      > generate questions from documents to prepare for metrics, check how many documents are returned by query
    - Dbs
      - elasticsearch
      - practice / @pavlik
    - Rerankings
      - practice / @pavlik
  - Retrieve & Summarize / 10 min / @pavlik
  - ~~Testing? / 20 min / @alex~~
- Summary / @alex @pavlik
  - Performance & Optimization Considerations
