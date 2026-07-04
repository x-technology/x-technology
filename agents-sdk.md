---
title: XTechnology Workshop - The Agent Runtime Workshop: Node.js, Tools, CI/CD
---

[![XTechnology - Technology is beautiful, let's discover it together!](https://user-images.githubusercontent.com/1259644/139526072-c2df5b3f-86b3-40eb-a91a-e51a307269ec.png)](https://xtechnology.dev/)

<style type="text/css">
  h1:first-child {
    display: none;
  }

  img[alt="autonomous agent 2023"],img[alt="alt text"],img[alt="function call flow"],img[alt="inspector"], img[alt="text splitter example"], img[alt="embeddings vs indexing"], img[alt="embedding space"], img[alt="what are embedding models"], img[alt="RAG Triad"], img[alt="reranking process"],
  img[alt="code agent work diagram"], img[alt="Planning"], img[alt="ANP"], img[alt="ANP Protocol Architecture"],
  img[alt="agent protocol use cases"], img:not([alt]), img[alt=""], img[alt*="normal size"] {
    width: 500px;
    max-height: 600px;
  }

  img[alt*="photo"], img[alt*="smaller"] {
    max-width: 300px !important;
    max-height: 300px;
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
  <a href="https://twitter.com/XTechnology5/status/1662440871936114688"><i></i></a>
</div>

# The Agent Runtime Workshop: Node.js, Tools, CI/CD, and Guardrails

The workshop focuses on theory and practice building production-ready AI agents with Node.js and modern Agent SDKs. We will use a real codebase as an execution environment to explain the core concepts behind agents: the agent loop, tool calling, structured outputs, context management, guardrails, tools, and human approval. We will build a Node.js SDK-based engineering agent that receives a development task, inspects a repository, proposes and applies safe code changes, runs validation checks, and exports execution artifacts to a messenger/storage. We will also cover how this agent fits into a broader production architecture: where MCP, orchestration, multi-agent patterns, CI/CD, security boundaries, observability, and workflow tools such as n8n may be useful.

By the end of the workshop, participants will understand not only how to use an Agent SDK, but also what remains their responsibility when designing safe and maintainable agent runtimes.

## Prerequisites

- Good understanding of JavaScript or TypeScript
- Experience with Node.js and API development
- Basic knowledge of databases and LLMs is helpful but not required

## Goals

- Understand AI agent and SDK architecture: loop, planning, memory, tools, guardrails
- Build a production-oriented engineering agent with an Agent SDK
- Apply sandboxing, permissions, approval gates, and observability
- Deploy agents locally and to cloud runtimes

## Code

- [Agents Workshop](https://github.com/x-technology/workshop-agents)

## Agenda

- [Introduction 📢](#introduction)
- [Setup 🛠️](#setup)
- [AI Agents World 🌎](#ai-agents-world)
- [Agents SDK 🧰](#agents-sdk)
- [Demo #1 - Build agents 🤖](#demo-1---build-agents)
- [Runtime 🔒](#runtime)
- [Deployment 🚀](#deployment)
- [Demo #2 - Deployment Aspects 🚢](#demo-2---deployment-aspects)
- [Summary 📚](#summary)
- [Feedback 💬](#feedback)
- [References 🔗](#references)

## Introduction

<!-- disclaimers: we are not DS, focus on usage, introduce high level and black box context -->

### Alex Korzhikov

![alex korzhikov photo](https://lh3.googleusercontent.com/d/1TMH5jMn5N5JXfK00uK2Ltti3CW8sULqP)

Software Engineer, Netherlands

My primary interest is self development and craftsmanship. I enjoy exploring technologies, coding open source and enterprise projects, teaching, speaking and writing about programming - JavaScript, Node.js, TypeScript, Go, Java, Docker, Kubernetes, JSON Schema, DevOps, Web Components, Algorithms 🎧 ⚽️ 💻 👋 ☕️ 🌊 🎾

- [AlexKorzhikov](https://www.linkedin.com/in/alex-korzhikov/)
- [korzio](https://github.com/korzio)

## Setup

- Node.js 18+
- OpenAI-compatible API key for live LLM demos is optional
- Gemini / Google API key for ADK demos is optional

Project setup:

```bash
git clone https://github.com/x-technology/workshop-agents.git
cd workshop-agents
npm install
```

Optional environment examples:

```bash
# Step 01 raw HTTP demo
export OPENAI_API_KEY=...
# optional:
export OPENAI_MODEL=gpt-4.1-mini
export OPENAI_BASE_URL=https://api.openai.com/v1
```

```bash
# Step 02 ADK demo with Gemini
export GOOGLE_API_KEY=...
# optional:
export GEMINI_MODEL=gemini-2.5-flash
```

```bash
# Step 02 ADK demo with OpenAI-compatible provider instead of Gemini
export SDK_PROVIDER=openai
export OPENAI_API_KEY=...
export OPENAI_MODEL=gpt-4o-mini
```

Default offline-friendly behavior:

- `npm run start:01` falls back to naive keyword routing if `OPENAI_API_KEY` is not set
- `npm run start:02` stays on the ADK path and falls back to a local keyword-based `BaseLlm`

## AI Agents World

| Aspect           | Gen AI                      | AI Agents                         | Agentic AI                                   |
| ---------------- | --------------------------- | --------------------------------- | -------------------------------------------- |
| Goal             | Generate content / answers  | Complete specific tasks           | Achieve complex goals autonomously           |
| Autonomy         | Low                         | Medium                            | High                                         |
| Planning         | None                        | Limited                           | Advanced                                     |
| Tool Use         | No                          | Yes                               | Yes (dynamic, multi-tool)                    |
| Memory           | Minimal (per session)       | Short / long-term                 | Persistent, contextual                       |
| Human Input      | High (prompt-driven)        | Medium (task oversight)           | Low (goal-driven)                            |
| Typical Use      | Q&A, summarization, writing | Booking, data fetching, workflows | Research, orchestration, decision-making     |
| Example Behavior | Responds to prompts         | Executes steps with tools         | Plans, adapts, and executes end-to-end tasks |

### IDE as a Code Agent

<!--
1. GenAI where we just prompting and expecting answers
2. AI Agent to act autonomously on a goal with tools and memory
-->

You're already [using one](https://agentskills.io/clients)!

- [Claude Code](https://code.claude.com)
- [Cursor](https://cursor.com)
- [GitHub Copilot](https://github.com/features/copilot)

### [RAG Recap](/rag#about-everything)

![rag](assets/rag.png)

### [LLM Agents vs Workflows](https://www.anthropic.com/engineering/building-effective-agents)

> - Workflows are systems where LLMs and tools are orchestrated through predefined code paths

### AI agents

> Systems where LLMs dynamically direct their own processes and tool usage, maintaining control over how they accomplish tasks

[![autonomous agent 2023](https://lilianweng.github.io/posts/2023-06-23-agent/agent-overview.png)](https://lilianweng.github.io/posts/2023-06-23-agent/)

A system that **autonomously** performing tasks on behalf of a user or another system by designing its workflow and utilizing available tools

<!-- autonomous - proactive, not reactive -->

**LLM** - Large Language Models trained on tons of sources and materials, having billions of parameters

**Loop** - Agent's fundamental core operating system

[![code agent work diagram](https://mintcdn.com/claude-code/gvy2DIUELtNA8qD3/images/agent-loop-diagram.svg?fit=max&auto=format&n=gvy2DIUELtNA8qD3&q=85&s=192e1bd6c8a2950a16e5ee0b94e27e26)](https://code.claude.com/docs/en/agent-sdk/agent-loop)

**[Planning](https://arxiv.org/pdf/2402.02716)** - task decomposition, multi-plan selection, external module-aided planning, reflection and refinement, memory-augmented planning, evaluation

![Planning smaller](https://www.researchgate.net/profile/Xu-Huang-37/publication/380756642/figure/fig1/AS:11431281246334630@1716345510279/Taxonomy-on-LLM-Agent-planning.png)

```math
p = (a0, a1, · · · , at) = plan(E, g; Θ, P).
g0, g1, · · · , gn = decompose(E, g; Θ, P);
pi = (ai0, ai1, · · · aim) = sub-plan(E, gi; Θ, P).
```

Prompt Architectures - **[Chain of Thought (CoT)](https://arxiv.org/abs/2201.11903)**, ReAct, PRACT, RAISE, Reflexion, ...

<!-- the model generates entire, multi-step plan upfront -->

```ts
// ReAct
while (true) {
  const response = await llm(messages, tools);

  if (response.tool_call) {
    const result = await runTool(response.tool_call);
    messages.push(result);
  } else {
    return response.output;
  }
}
```

```ts
// Reflexion
export async function reflexionLoop(task: string) {
  let bestAnswer = null;
  let bestScore = -Infinity;

  for (let i = 0; i < 3; i++) {
    console.log(`Attempt ${i + 1}`);

    const trajectory = await runAgent(task);
    const evaluation = await evaluateTrajectory(task, trajectory);
    const reflection = await reflect(task, trajectory, evaluation);

    storeReflection(reflection);

    console.log("Score:", evaluation.score);
    console.log("Lessons:", reflection.lessons);

    if (evaluation.score > bestScore) {
      bestScore = evaluation.score;
      bestAnswer = trajectory.finalAnswer;
    }
  }

  return bestAnswer;
}
```

**Memory** - the processes used to gain, store, retain, and later retrieve information. Context engineering, **Short-term** (trigger, prompt, session) vs **long-term** (db, rag) memory.

<!-- Context engineering is preparing and feeding proper context to agents -->

**Tools** - extend LLM with ability to act outside its context - read data (files, APIs, web), compute (code execution), act (send email, write DB, click UI)

## Agents SDK

|                                 | **[Claude Agent SDK](https://code.claude.com/docs/en/agent-sdk/typescript)** | **[OpenAI Agents SDK](https://developers.openai.com/api/docs/guides/agents/define-agents)** | **[Google ADK](https://adk.dev/get-started/typescript/)** | **[AI SDK Vercel](https://ai-sdk.dev/docs/introduction)** | **[LangChain](https://docs.langchain.com/oss/javascript/langchain/overview)** |
| ------------------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- | ----------------------------------------------------------------------------- |
| **Primary purpose**             | Runtime for Claude-based agents with tool use + MCP                          | Build multi-step agents on OpenAI APIs                                                      | Build agents on Gemini / Vertex AI                        | Fullstack AI toolkit (not agent-first)                    | Composable chains, agent flows                                                |
| **Languages**                   | TypeScript, Python ⚠️ _(Python partial)_                                     | TypeScript, Python                                                                          | Python, TypeScript, Go, and Java                          | TypeScript / JavaScript                                   | Python, TypeScript                                                            |
| **Model support**               | Claude only                                                                  | OpenAI (⚠️ LiteLLM workaround)                                                              | Model-agnostic                                            | Model-agnostic                                            | Model-agnostic                                                                |
| **Orchestration & Multi-agent** | Subagents, tool loops, hooks; basic multi-agent orchestration                | Agents + handoffs; native multi-agent support                                               | Pipelines (seq/parallel); A2A protocol (early stage)      | Tool-based loops, limited multi-agent                     | Chains, agent executors                                                       |
| **Loop control**                | ⚠️ Hooks into steps, loop is internal                                        | ❌ Hidden — tools + instructions only                                                       | ⚠️ Orchestration-based, not loop-level                    | ❌ Loop is internal                                       | Partial via chains                                                            |
| **Tools**                       | MCP, bash, browser, file system                                              | Function calling, tools, MCP                                                                | Google tools + functions ⚠️ _(MCP maturity?)_             | Tool calling, MCP                                         | Tool calling, MCP                                                             |
| **Memory**                      | CLAUDE.md + runtime context ⚠️ _(not true long-term memory)_                 | Threads + state                                                                             | Vertex memory ⚠️ _(needs validation depth)_               | Per-request (stateless by default)                        | Buffers + vector DB                                                           |
| **Best fit**                    | Tool-heavy automation agents                                                 | Fast production agents                                                                      | Google ecosystem                                          | AI web apps                                               | Flexible agent flows, prototyping                                             |

### ADK (Google)

> Build production agents, not prototypes.
> ADK is the open-source agent development framework that lets you build, debug, and deploy reliable AI agents at enterprise scale. Available in Python, TypeScript, Go, Java, and Kotlin.

> ADK developer Skills

- [Skills](https://adk.dev/skills/)

```bash
npm install @google/adk
npm install -D @google/adk-devtools
npx adk web
```

```ts
import { FunctionTool, LlmAgent } from "@google/adk";
import { z } from "zod";

/* Mock tool implementation */
const getCurrentTime = new FunctionTool({
  name: "get_current_time",
  description: "Returns the current time in a specified city.",
  parameters: z.object({
    city: z
      .string()
      .describe("The name of the city for which to retrieve the current time."),
  }),
  execute: ({ city }) => {
    return {
      status: "success",
      report: `The current time in ${city} is 10:30 AM`,
    };
  },
});

export const rootAgent = new LlmAgent({
  name: "hello_time_agent",
  model: "gemini-flash-latest",
  description: "Tells the current time in a specified city.",
  instruction: `You are a helpful assistant that tells the current time in a city.
                Use the 'getCurrentTime' tool for this purpose.`,
  tools: [getCurrentTime],
});
```

Key features:

- [Agent loop](https://code.claude.com/docs/en/agent-sdk/agent-loop)
- Model-agnostic
- Deployment-agnostic
- Built-in tools - file operations, web Search, execution. Compare [claude](https://code.claude.com/docs/en/agent-sdk/agent-loop#built-in-tools) VS [openai](https://openai.github.io/openai-agents-js/guides/tools/?utm_source=chatgpt.com#1-hosted-tools-openai-responses-api)

## Demo #1 - Build agents

- Claude Agent SDK
- Google ADK

## Runtime

- [Security Aspects](https://code.claude.com/docs/en/agent-sdk/secure-deployment), [adk](https://adk.dev/safety/)

- Isolation
  - [Sandboxing](https://code.claude.com/docs/en/sandboxing)
  - [Example in docker](https://code.claude.com/docs/en/agent-sdk/secure-deployment#containers)
- Least privilege
  - Tools have permission settings to allow, block, or prompt the user for approval
  - Limit file, network, credentials access with proxy

```ts
options: {
  allowedTools: ["Read", "Glob", "Grep"],
  permissionMode: "acceptEdits",
  continue: true
},
```

- Defense in depth
  - Security Schemes - Authentication options
  - Contract-first tools
  - Code and Web responses auto-checks
  - Guardrails - Control your model and tool calls [with built-in, custom or external hooks](https://adk.dev/safety/#callbacks-and-plugins-for-security-guardrails)
  - Human-in-the-Loop
  - Decrease temperature and context
  - Define budget

```sh
docker run \
  --cap-drop ALL \
  --security-opt no-new-privileges \
  --security-opt seccomp=/path/to/seccomp-profile.json \
  --read-only \
  --tmpfs /tmp:rw,noexec,nosuid,size=100m \
  --tmpfs /home/agent:rw,noexec,nosuid,size=500m \
  --network none \
  --memory 2g \
  --cpus 2 \
  --pids-limit 100 \
  --user 1000:1000 \
  -v /path/to/code:/workspace:ro \
  -v /var/run/proxy.sock:/var/run/proxy.sock:ro \
  agent-image
```

- [Observability](https://adk.dev/observability/) - [Tracing](https://adk.dev/observability/traces/#gcp-export-setup) and Logging

## Deployment

| Option                              | Description                                                                                          |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Local**                           | Self-hosted runtime, full control over environment, container, and secrets                           |
| **Cloud — Claude Managed Agents**   | Provider-managed sessions, sandbox, event stream; deploy via `platform.claude.com/.../deployments`   |
| **Cloud — Google ADK on Cloud Run** | Agent as a cloud-native service; Cloud Run provides container runtime, HTTPS, IAM, autoscaling, logs |
| **Monolith**                        | Configurable native client                                                                           |

### Local

Run the agent runtime in a local container or directly in your Node.js environment. Useful for development, testing, and offline execution.

### Claude Managed Agents

> Claude SDK as a coding-native agent runtime.
> Claude Managed Agents as the native deployment path.

Deploy versioned agent configurations via `platform.claude.com/.../deployments`. Managed sessions, built-in sandbox, event stream, and cloud or self-hosted environments are included.

### Google ADK on Cloud Run

ADK defines:

```txt
agent
tools
workflow
model behavior
```

Cloud Run provides:

```txt
container runtime
HTTPS endpoint
IAM
autoscaling
logs
revisions
env/secrets integration
```

> ADK is built for deploy anywhere flexibility. You can containerize and run ADK on your own infrastructure, or take advantage of our native, one-command deployment to Google Cloud. When deploying to Google Cloud via Agent Runtime (Agent Platform), Cloud Run, or GKE, your agents instantly inherit managed infrastructure, built-in authentication, Cloud Trace observability, and enterprise-grade security—all without requiring you to change a single line of your agent code. Develop locally, scale globally.

### Monolith Agent Deployment

```bash
claude -p "say hi"
```

## Demo #2 - Deployment Aspects

- [Github Issue Pipeline](https://github.com/XXX/Test/issues)

## Summary

An agent runtime is a control plane — coordination, policy, memory, and tooling around an LLM. Node.js fits well as that plane, and Agent SDKs give you the building blocks: tool calling, structured outputs, sessions, guardrails, and tracing. Production readiness comes from sandboxing, approval gates, observability, and connecting the agent to real CI/CD and deployment targets.

## Feedback

Please share your feedback on the workshop. Thank you and have a great coding!

<!-- Feedback link TBD -->

If you like the workshop, you can become our [patron](https://www.patreon.com/xtechnology), yay! 🙏

## References

- [Building effective agents - Engineering at Anthropic Dec 19, 2024](https://www.anthropic.com/engineering/building-effective-agents)
- [LLM Zoomcamp - A Free Course on Real-Life Applications of LLMs](https://github.com/DataTalksClub/llm-zoomcamp)
- [A Survey of AI Agent Protocols](https://arxiv.org/abs/2504.16736)
- [Lilian Weng - LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)
- [Awesome AI Agent Protocols](https://github.com/zoe-yyx/Awesome-AIAgent-Protocol)
- [Understanding the planning of LLM agents: A survey, 5 Feb 2024](https://arxiv.org/pdf/2402.02716)
- [A2A: The Agent2Agent Protocol - DeepLearning.ai](https://learn.deeplearning.ai/courses/a2a-the-agent2agent-protocol)
- [A2A and MCP: Detailed Comparison](https://a2a-protocol.org/latest/topics/a2a-and-mcp/)
- [Agent Skills Overview](https://agentskills.io/home)

### Technologies

- LLM
- AI Agents
- MCP
- Agent SDKs
- ADK
- Claude
