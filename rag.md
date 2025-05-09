---
title: XTechnology Workshop - Building a RAG System in Node.js: Vector Databases, Embeddings & Chunking
---

[![XTechnology - Technology is beautiful, let's discover it together!](https://user-images.githubusercontent.com/1259644/139526072-c2df5b3f-86b3-40eb-a91a-e51a307269ec.png)](https://xtechnology.dev/)

<style type="text/css">
  h1:first-child {
    display: none;
  }

  img[alt="text splitter example"], img[alt="embeddings vs indexing"], img[alt="embedding space"], img[alt="what are embedding models"], img[alt="RAG Triad"], img[alt="reranking process"] {
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
- [About Everything 🌎](#about-everything)
- [Setup 🛠️](#setup)
- [Practice #1 - Hello World 👋](#practice-1---hello-world)
- [Use Case - Exploring Node.js News 📰](#use-case---exploring-nodejs-news)
- [Chunking ✂️](#chunking)
- [Practice #2 - Chunking 🧩](#practice-2---chunking)
- [Store & Retrieve 🗂️](#store--retrieve)
- [Practice #3 - Store & Retrieve 🔍](#practice-3---store--retrieve)
- [Reranking 🥇](#reranking)
- [Evaluation 📊](#evaluation)
- [Practice #4 - Evaluation 🧪](#practice-4---evaluation)
- [Summary 📚](#summary)
- [Feedback 💬](#feedback)
- [Links 🔗](#links)

## Introduction

<!-- disclaimers: we are not DS, focus on usage, introduce high level and black box context -->

- Explore RAG's scope, architecture and components
- Practice various RAG aspects with chosen technologies
- Feedback & evaluate

### Alex Korzhikov

![alex korzhikov photo](https://github.com/x-technology/PizzaScript/blob/main/assets/alex-black-white-open-source.png?raw=true)

Software Engineer, Netherlands

My primary interest is self development and craftsmanship. I enjoy exploring technologies, coding open source and enterprise projects, teaching, speaking and writing about programming - JavaScript, Node.js, TypeScript, Go, Java, Docker, Kubernetes, JSON Schema, DevOps, Web Components, Algorithms 🎧 ⚽️ 💻 👋 ☕️ 🌊 🎾

- [AlexKorzhikov](https://www.linkedin.com/in/alex-korzhikov-8614011a/)
- [korzio](https://github.com/korzio)

### Pavlik Kiselev

![Pavlik](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/team/pavlik.jpg?raw=true)

Software Engineer, Netherlands

JavaScript developer with full-stack experience and frontend passion. He happily works at ING in a Fraud Prevention department, where helps to protect the finances of the ING customers.

- [Pavlik Kiselev](https://www.linkedin.com/in/pavlik-kiselev-06993347/)
- [paulcodiny](https://github.com/paulcodiny)

## About Everything

### Generative Artificial Intelligence (GenAI)

Use of Artificial Intelligence to produce human consumable content in **text**, image, audio, video format.

### Language Model (LM)

Language Models are Machine Learning models trained on natural language resources and aim predict next word based on given context.

LM relevant tasks - summarization, Q&A, classification, and more.

### Large Language Model (LLM)

Artificial Intelligence is powered by Large Language Models - models trained on tons of sources and materials, having billions of parameters.

![llm as blackbox](assets/llm-blackbox.png)

### Retrieval Augmented Generation (RAG)

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

<details><summary>Why do we need RAG?</summary>
- Additional, specific knowledge<br>
- Reduce hallucinations<br>
- Control system costs<br>
</details>

<details><summary>Why can't we just put all context in our LLM and ask it about?</summary>
- Cost<br>
- Slow<br>
- Size<br>
- Noize<br>
</details>

<details><summary>What do we need to build a RAG?</summary>
- Application (backend)<br>
- Search system (vector databases)<br>
- LLM (blackbox)<br>
</details>

### [Langchain](https://js.langchain.com/docs/introduction/) 🦜️🔗

> LangChain is a Python and JavaScript framework that brings flexible abstractions and AI-first toolkit for developers to build with GenAI and integrate your applications with LLMs. It includes components for abstracting and chaining LLM prompts, configure and use vector databases (for semantic search), document loaders and splitters (to analyze documents and learn from them), output parsers, and more.

## Setup

- Node.js
- Ollama / OpenAI
- `npm i langchain`

## Practice #1 - Hello World

```js
ollama.chat({
  messages: [
    { role: "user", content: "What is retrieval-augmented generation?" },
  ],
});
```

## Use Case - Exploring Node.js News

<video width="50%" height="500px" controls>
  <source src="https://framerusercontent.com/assets/Syj9M1soD3kB2EvO4GeoATDATI.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

We aim to understand what happened in the Node.js community over the past year. To achieve this, we:
1. Collect and process news, popular blog posts, and articles
2. Store the documents in a database
3. Analyze and query the documents by asking targeted questions

<iframe src="https://atlas.nomic.ai/data/todexex279/nodejs-v4-2024/map" width="50%" height="500px"></iframe>

### How do we find sources?
- Own collection
- Ask ChatGPT <i>What are the best online resource to follow on Node.js news? Output urls and short description</i>

### How do we scrap articles?

- Direct fetch requests
- Run browser and navigate to urls
- Use external [services](https://console.apify.com/actors/tasks/mhbgzDv598tdTbltb/input)

### Some scrapping and text quality problems

- Paywalls
- Anti-bot protections
  - Cat & mouse game
- [Noise](https://github.com/x-technology/tech-people-stats/tree/feat/js-langchain/experiments/nodejs-v2/text-links-dataset_ai-web-scraper---extracted-urls-v2_2024-01-13_15-46-37-422.json) (marketing texts, tags, js, css)
  - Clean & parse
  - Noise reduction [algorithms](https://github.com/x-technology/tech-people-stats/blob/feat/js-langchain/langchain/parse-body.js)

### [Articles](https://github.com/x-technology/rag-workshop/blob/main/assets/articles.json)

- What dataset do you have?
- Which format do you need to parse?
- What are the most often queries?

## Chunking

### To chunk or not to chunk?

[![text splitter](https://python.langchain.com/assets/images/text_splitters-7961ccc13e05e2fd7f7f58048e082f47.png)](https://python.langchain.com/docs/concepts/text_splitters/)

> Chunking involves breaking down texts into smaller, manageable pieces called "chunks". Each chunk becomes a unit of information that is vectorized and stored in a database, fundamentally shaping the efficiency and effectiveness of natural language processing tasks.

- Normalize documents
- Reduce context (latency, LLM usage & cost)
- Enhance retrieval precision

### How do we split documents?

[![text splitter example](assets/text-splitter-online.png)](https://chunkviz.up.railway.app/)

- Chunk Size
> The number of characters we would like in our chunks. 50, 100, 100,000, etc.

- Chunk Overlap
> The amount we would like our sequential chunks to overlap. This is to try to avoid cutting a single piece of context into multiple pieces. This will create duplicate data across chunks.

- Length-based (`CharacterTextSplitter`) - Easy & Simple, don't take into account the text's structure

- Character/Token [splitters](https://textsplittervisualizer.com/)

```js
const { CharacterTextSplitter } = require("@langchain/textsplitters");
const textSplitter = new CharacterTextSplitter({
  chunkSize: 100,
  chunkOverlap: 0,
});
const texts = await textSplitter.splitText(document)
```

- Text-structured based (`RecursiveCharacterTextSplitter`)

- What split characters do you think [are included](https://github.com/langchain-ai/langchain/blob/9ef2feb6747f5a69d186bd623b569ad722829a5e/libs/langchain/langchain/text_splitter.py#L842) in Langchain by default?

- [Document-structured based](https://python.langchain.com/docs/how_to/code_splitter/)

- Semantic meaning based - [Extract Propositions](https://chentong0.github.io/factoid-wiki/)

- Agentic Chunking
  - Summarize text, propositions, images
  - Generate hypothetical questions
  - [Multiple embeddings](https://js.langchain.com/docs/how_to/multi_vector/)

## Practice #2 - Chunking
```js
const { RecursiveCharacterTextSplitter } = require("@langchain/textsplitters");
const splitter = new RecursiveCharacterTextSplitter({
  chunkSize: 100,
  chunkOverlap: 0,
});

return await splitter.splitText(text);
```

## Store & Retrieve

![what are embedding models](https://ollama.com/public/blog/what-are-embeddings.svg)

- Semantic VS Keyword Search

### To embed or not?

An embedding is a vector representation of data in embedding space (projecting the high-dimensional space of initial data vectors into a lower-dimensional space).

![embeddings vs indexing](assets/docs-index.png)

Vectors are stored in a database, which compare them as a way to search for data that is similar in meaning (by using [dot product](https://en.wikipedia.org/wiki/Dot_product) or [cosine](https://en.wikipedia.org/wiki/Cosine_similarity) measurement).

[![embedding space](https://developers.google.com/static/machine-learning/crash-course/images/embeddings_3D_tangyuan.png)](https://developers.google.com/machine-learning/crash-course/embeddings/embedding-space)

- [Ollama supported embedding models](https://ollama.com/search?c=embedding)

<details><summary>Can we exchange embedding models with equal vector dimensions?</summary>
- Nope, also embedding models evolve over time<br>
<img src="https://i.kym-cdn.com/photos/images/original/002/086/808/90f.gif" alt="obvious reaction"/>
</details>

## Practice #3 - Store & Retrieve
```js
await Chroma.fromTexts(
  texts,
  { id: Array.from({ length: texts.length }, (_, i) => `chunk-${i}`) },
  embeddings,
  { collectionName: "rag_node_workshop_articles" },
);
```
## Reranking

![reranking process](./assets/reranking.png)

> Rerankers analyze the initial search output and adjust the ranking to better match user preferences and application requirements

- Improve quality (other models and more context involved)
- Cost considerations
- Vector VS LLM based

## Evaluation

![RAG Triad](https://d2lsxfc3p6r9rv.cloudfront.net/rag-triad.svg)

> Evaluate RAG the retriever and generator of a RAG pipeline separately

### Retriever

Hyperparameters:
- Database
- Embedding model
- Chunk size
- Top-K documents
- LLM temperature
- Prompt template
- Reranking model
- etc.

> Does your reranker model ranks the retrieved documents in the "correct" order?

Metrics:
- Precision - whether documents in the retrieved context that are relevant to the given input are ranked higher than irrelevant ones
- Recall - how well the retrieved context aligns with the expected output, or if all relevant documents are retrieved

### Generation

Hyperparameters:
- Prompt template
- LLM

> Can we use a smaller, faster, cheaper LLM?

Metrics:
- Faithfulness / Groundedness - whether the actual output factually aligns with the retrieved context
- Answer relevancy - how relevant the actual output is to the provided input

### Frameworks

- [DeepEval](https://docs.confident-ai.com/)
- [TruLens](https://www.trulens.org/)
- [Ragas](https://docs.ragas.io/en/latest/getstarted/)

### Our choice

- Hit Rate (HR) or Recall at k:
Measures the proportion of queries for which at least one relevant document is retrieved in the top k results.

- Mean Reciprocal Rank (MRR):
Evaluates the rank position of the first relevant document.

- Chunk attributions/utilization - if chunk contributed to model/rag response

- What low numbers might show us?
- How do we define numbers?

## Practice #4 - Evaluation
```js
const relevantDocs = await getRelevantDocuments(vectorStore, summary);
const relevance = relevantDocs.map((d) => d.pageContent === chunk);
console.log(hitRate(relevance));
```

## Summary

## Feedback

Please [share your feedback](https://app.sli.do/event/wV641HGAr8jeVnULeLAAg2) on the workshop. Thank you and have a great coding!

<iframe src="https://wall.sli.do/event/wV641HGAr8jeVnULeLAAg2/?section=fdc6bb93-244d-4320-ac2d-cd6a3ffd6a38" width="50%" height="500px"></iframe>

If you like the workshop, you can become our [patron](https://www.patreon.com/xtechnology), yay! 🙏

## Links

- [Mete Atamel - A blog about software development and more](https://atamel.dev/)
- [Build a Retrieval Augmented Generation (RAG) App](https://js.langchain.com/docs/tutorials/rag/)
- [5 Levels Of Text Splitting](https://github.com/FullStackRetrieval-com/RetrievalTutorials/blob/main/tutorials/LevelsOfTextSplitting/5_Levels_Of_Text_Splitting.ipynb)
- [LlamaIndex - End-to-end tooling to ship a context-augmented AI agent to production](https://llama-playground.vercel.app/)
- [Ragas - Ultimate toolkit for evaluating and optimizing Large Language Model (LLM) applications.](https://github.com/explodinggradients/ragas)
- [deepeval - the open-source LLM evaluation framework](https://docs.confident-ai.com/)
- [LLM Zoomcamp - A Free Course on Real-Life Applications of LLMs](https://github.com/DataTalksClub/llm-zoomcamp)
- [Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course/embeddings/)
- [DeepEval - RAG Evaluation](https://docs.confident-ai.com/guides/guides-rag-evaluation)
- [Cohere - Say Goodbye to Irrelevant Search Results: Cohere Rerank Is Here](https://cohere.com/blog/rerank)
- [5-Day Gen AI Intensive Course with Google Learn Guide](https://www.kaggle.com/learn-guide/5-day-genai)

### Technologies

- LLM
- Langchain
- RAG