---
title: XTechnology Workshop - Operating Agent-Based Systems - Overview, Configure, Run, Orchestrate, Monitor
---

[![XTechnology - Technology is beautiful, let's discover it together!](https://user-images.githubusercontent.com/1259644/139526072-c2df5b3f-86b3-40eb-a91a-e51a307269ec.png)](https://xtechnology.dev/)

<style type="text/css">
  h1:first-child {
    display: none;
  }

  img[alt="autonomous agent 2023"],img[alt="alt text"],img[alt="function call flow"],img[alt="inspector"], img[alt="text splitter example"], img[alt="embeddings vs indexing"], img[alt="embedding space"], img[alt="what are embedding models"], img[alt="RAG Triad"], img[alt="reranking process"] {
    width: 500px;
    max-height: 600px;
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

# Drafts

Operating Agent-Based Systems - Overview, Configure, Run, Orchestrate, Monitor

This workshop explores how standalone agents operate at the runtime level and how they differ from traditional AI pipelines. We’ll examine agent architecture, planning loops, memory models, and tool execution. We’ll also cover multi-agent coordination, including state isolation and resource control. A key focus is security and governance — capability-based access, sandboxing, and injection risks. Finally, we’ll address observability and supervision: tracing reasoning, auditing tool usage, and implementing control mechanisms for production systems.

All examples and concepts will be grounded in the Node.js stack and we will explore why Node.js is particularly well-suited for building production-ready agent runtimes — serving as the control plane for supervision, integration, streaming execution, and distributed coordination.

references: OpenClaw, n8n, LangChain

Пока что такой план обсудили на воркшоп
1. Теория про агентов. Что такое вообще
2. Разработка агента "на коленке"
3. Теория про SDK для агентов (посмотрю варианты)
4. Разработка агента на SDK.
5. Теория про оркестрацию. Что делать, когда агентов несколько
6. Разработка ещё одного-двух агентов и встраивание его в n8n
7. Теория общих правил оркестрации. Безопасность, мониторинг и т.д.
8. Практика
9. Конец

## 2026-04-28

- [ ] what are stop execute evaluation practices?
- [ ] does n8n use a2a?

## 2026-04-22

- [ ] need to try play with skills in artificial project

## 2026-04-21

- [x] need to try out next time with docker image

## 2026-04-20

read about [claude sdk ](https://code.claude.com/docs/en/agent-sdk/claude-code-features)

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
- [Setup 🛠️](#setup)

## Introduction

<!-- disclaimers: we are not DS, focus on usage, introduce high level and black box context -->

- Explore RAG's scope, architecture and components
- Demo various RAG aspects with chosen technologies
- Feedback & evaluate

### Alex Korzhikov

![alex korzhikov photo](https://github.com/x-technology/PizzaScript/blob/main/assets/alex-black-white-open-source.png?raw=true)

Software Engineer, Netherlands

My primary interest is self development and craftsmanship. I enjoy exploring technologies, coding open source and enterprise projects, teaching, speaking and writing about programming - JavaScript, Node.js, TypeScript, Go, Java, Docker, Kubernetes, JSON Schema, DevOps, Web Components, Algorithms 🎧 ⚽️ 💻 👋 ☕️ 🌊 🎾

- [AlexKorzhikov](https://www.linkedin.com/in/alex-korzhikov/)
- [korzio](https://github.com/korzio)

### Pavlik Kiselev

![Pavlik](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/team/pavlik.jpg?raw=true)

Software Engineer, Netherlands

JavaScript developer with full-stack experience and frontend passion. He happily works at ING in a Fraud Prevention department, where helps to protect the finances of the ING customers.

- [Pavlik Kiselev](https://www.linkedin.com/in/pavlik-kiselev-06993347/)
- [paulcodiny](https://github.com/paulcodiny)

## Setup

- Node.js
- Ollama / OpenAI
- `npm i langchain`

## AI Agents World

- [Agents vs Workflows](https://www.anthropic.com/engineering/building-effective-agents)

> - Workflows are systems where LLMs and tools are orchestrated through predefined code paths.
> - Agents, on the other hand, are systems where LLMs dynamically direct their own processes and tool usage, maintaining control over how they accomplish tasks.

  - RAG Example

- AI agents

[![autonomous agent 2023](https://lilianweng.github.io/posts/2023-06-23-agent/agent-overview.png)](https://lilianweng.github.io/posts/2023-06-23-agent/)

> AI agents are AI programs built on top of LLMs. They use LLM information-processing capabilities to obtain data, make decisions, and take actions on behalf of human users.

> Agents can be used for open-ended problems where it’s difficult or impossible to predict the required number of steps, and where you can’t hardcode a fixed path.

![code agent work diagram](https://mintcdn.com/claude-code/gvy2DIUELtNA8qD3/images/agent-loop-diagram.svg?fit=max&auto=format&n=gvy2DIUELtNA8qD3&q=85&s=192e1bd6c8a2950a16e5ee0b94e27e26)
  - LLM
  - Loop
  - Planning
    - Evaluation
  - Memory
  - Tools
    > ways for an LLM to act outside its context - read data (files, APIs, web), compute (code execution), act (send email, write DB, click UI)
    - MCP
  - Guardrails
  - components - memory, llm, reasoning, research models, guardrails

Agent architectures: ReAct, PRACT, RAISE, Reflexion


<!-- > Agents are AI systems that can:
>
> Make decisions about what actions to take
> Use tools to accomplish tasks
> Maintain state and context
> Learn from previous interactions
> Work towards specific goals
> Agentic flow is not necessarily a completely independent agent, but it can still make some decisions during the flow execution
>
> A typical agentic flow consists of:
>
> Receiving a user request
> Analyzing the request and available tools
> Deciding on the next action
> Executing the action using appropriate tools
> Evaluating the results
> Either completing the task or continuing with more actions
> The key difference from basic RAG is that agents can:
>
> Make multiple search queries
> Combine information from different sources
> Decide when to stop searching
> Use their own knowledge when appropriate
> Chain multiple actions together
>
> So in agentic RAG, the system
> has access to the history of previous actions
> makes decisions independently based on the current information and the previous actions
![alt text](assets/mcp-deep-dive.png)

https://www.anthropic.com/engineering/building-effective-agents

> "Agent" can be defined in several ways. Some customers define agents as fully autonomous systems that operate independently over extended periods, using various tools to accomplish complex tasks. Others use the term to describe more prescriptive implementations that follow predefined workflows. At Anthropic, we categorize all these variations as agentic systems, but draw an important architectural distinction between workflows and agents:

Workflows are systems where LLMs and tools are orchestrated through predefined code paths.
Agents, on the other hand, are systems where LLMs dynamically direct their own processes and tool usage, maintaining control over how they accomplish tasks.

> MCP is one way for AI agents to find the information they need and to take actions. It helps connect AI agents to the "outside world," so to speak — the world beyond the LLM's training data. (Other methods include API integrations and headless browsing.)

> an LLM agent typically consists of:
> - Foundation Model,  typically a large language model or a multimodal large model,
which provides essential capabilities for reasoning, understanding language, and interpreting multimodal information
> - Memory Systems: LLM agents implement both short-term and long-term memory components to maintain context across interactions and store relevant information for future use
> - Planning: Planning is a fundamental aspect of agent research (), enabling agents to break down complex tasks into smaller, manageable subtasks
> - Tool-Using: Although LLMs inherently face limitations in mathematical reasoning, logical operations, and knowledge beyond their trained corpus, agents overcome these constraints by integrating external tools and APIs
> - Action Execution: The ability to interact with their environment by executing actions, whether through API calls, database queries, or interaction
with external systems.
-->

## Agents SDK

Frameworks: CrewAI, LangGraph, MetaGPT
- The [Claude Agent SDK](https://code.claude.com/docs/en/agent-sdk/typescript#query);
- Strands Agents SDK by AWS;
- Rivet, a drag and drop GUI LLM workflow builder; and
- Vellum, another GUI tool for building and testing complex workflows.
- [AI SDK Vercel](https://ai-sdk.dev/docs/introduction)

claude

https://code.claude.com/docs/en/agent-sdk/agent-loop

### [Example in docker](https://code.claude.com/docs/en/agent-sdk/secure-deployment#containers)

openai

https://developers.openai.com/api/docs/guides/agents/define-agents#when-to-split-one-agent-into-several

### [Langchain](https://js.langchain.com/docs/introduction/) 🦜️🔗

> LangChain is a Python and JavaScript framework that brings flexible abstractions and AI-first toolkit for developers to build with GenAI and integrate your applications with LLMs. It includes components for abstracting and chaining LLM prompts, configure and use vector databases (for semantic search), document loaders and splitters (to analyze documents and learn from them), output parsers, and more.

OpenClaw

## Agent Protocols

![[what is a2a](https://a2a-protocol.org/latest/topics/what-is-a2a/#understanding-the-agent-stack-a2a-mcp-agent-frameworks-and-models)](https://a2a-protocol.org/latest/assets/agentic-stack.png)

> Agent protocols are standardized frameworks that define the rules, formats, and procedures for structured communication among agents and between agents and external systems

- MCP
- [Agent-to-Agent (A2A)](https://github.com/a2aproject/A2A)
- [ANP - Agent Network Protocol](https://www.agent-network-protocol.com/)

[![alt text](assets/mcp-agents-ecosystem.png)](https://arxiv.org/abs/2504.16736)

[![alt text](assets/mcp-ai-dev-timeline.png)](https://arxiv.org/abs/2504.16736)

## Aspects

- Security

https://code.claude.com/docs/en/agent-sdk/secure-deployment

## Summary

The workshop overviews and ...

## Feedback

Please [share your feedback](https://app.sli.do/event/wV641HGAr8jeVnULeLAAg2) on the workshop. Thank you and have a great coding!

<iframe src="https://wall.sli.do/event/wV641HGAr8jeVnULeLAAg2/?section=fdc6bb93-244d-4320-ac2d-cd6a3ffd6a38" width="50%" height="500px"></iframe>

If you like the workshop, you can become our [patron](https://www.patreon.com/xtechnology), yay! 🙏

## Links

- [Building effective agents - Engineering at Anthropic Dec 19, 2024](https://www.anthropic.com/engineering/building-effective-agents)
- [LLM Zoomcamp - A Free Course on Real-Life Applications of LLMs](https://github.com/DataTalksClub/llm-zoomcamp)
- [A Survey of AI Agent Protocols](https://arxiv.org/abs/2504.16736)
- [Lilian Weng - LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)

### Technologies

- LLM
- Langchain
- RAG
- AI Agents
- MCP