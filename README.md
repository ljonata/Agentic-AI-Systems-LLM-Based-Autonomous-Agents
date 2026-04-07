# Agentic AI Systems: LLM-Based Autonomous Agents

---

## Instructor

**Luiz Araujo, Ph.D.** — [LinkedIn](https://www.linkedin.com/in/luiz-jonata-pires-de-araujo/) · [ResearchGate](https://www.researchgate.net/profile/Luiz-Araujo-6)

AI/ML engineer, data scientist, and academic with 20+ years in software development and a Ph.D. in Computer Science from the University of Nottingham (UK). His expertise spans Natural Language Processing, Large Language Models, and agentic AI systems. Previously a Senior Lecturer and Honorary Fellow Researcher at the University of Lincoln (UK), where he led Master's-level modules in Advanced Software Engineering and Data Engineering.

---

## Tech Stack Overview
| Layer | Tools |
|---|---|
| **LLM APIs** | Anthropic Claude, OpenAI GPT-4o |
| **Agent Frameworks** | LangChain, LangGraph, AutoGen, CrewAI |
| **Protocols** | MCP (Model Context Protocol), OpenAI function calling |
| **Memory / Vector DBs** | ChromaDB, Pinecone, FAISS |
| **Observability** | LangSmith, Arize Phoenix, Weights & Biases |
| **GUI / Browser Agents** | Playwright, Selenium, Anthropic Computer Use |
| **Evaluation** | AgentBench, SWE-bench, custom harnesses |
| **Infrastructure** | Docker, FastAPI, Modal, AWS Lambda |

---

## Week 1 — Introduction to Agentic AI
**Topics**
- LLMs as reasoning engines and agents
- Agent architecture (loop, tools, memory)
- From prompts to autonomous systems

**Papers**
- Brown et al. (2020) — Language Models are Few-Shot Learners
- Bommasani et al. (2021) — Foundation Models

**Lab**
Set up the course environment. Make your first API calls to Claude and GPT-4o. Implement a minimal agent loop (input → LLM → output → repeat) from scratch in Python with no frameworks.

**Tech Stack:** Python, Anthropic SDK, OpenAI SDK

---

## Week 2 — LLM Reasoning Patterns
**Topics**
- Chain-of-Thought prompting
- Self-consistency
- Tree-of-Thought
- Reasoning failure modes

**Papers**
- Wei et al. (2022) — Chain-of-Thought Prompting Elicits Reasoning 
- Wang et al. (2022) — Self-Consistency Improves Chain of Thought Reasoning 

**Lab**
Implement CoT, self-consistency (majority voting across N samples), and a simple Tree-of-Thought explorer for a logic puzzle. Compare accuracy across strategies on a small benchmark.

**Tech Stack:** Python, Anthropic SDK, NumPy

---

## Week 3 — ReAct, Tool Use & Function Calling
**Topics**
- Thought–Action–Observation loop
- Function calling and API integration
- Structured outputs
- Iterative reasoning with tools

**Papers**
- Yao et al. (2022) — ReAct: Synergizing Reasoning and Acting 
- Schick et al. (2023) — Toolformer 

**Lab**
Build a ReAct agent with 3 tools: a calculator, a web search stub, and a Wikipedia lookup. Implement the TAO loop manually, then replicate it using LangChain. Compare verbosity and control.

**Tech Stack:** Python, LangChain, Anthropic SDK, Wikipedia API

---

## Week 4 — Structured Agent Protocols
**Topics**
- Model Context Protocol (MCP) — tool and resource standardization
- Agent-to-Agent (A2A) communication protocols
- OpenAI function calling schema vs MCP
- Why protocols matter for interoperability and safety

**Papers / Resources**
- Anthropic MCP specification (2024) 
- Google A2A Protocol proposal (2025) 

**Lab**
Build an MCP-compliant tool server (e.g. a file reader + summarizer) and connect it to a Claude agent. Then swap the client to a different LLM to demonstrate protocol interoperability.

**Tech Stack:** Python, MCP SDK, FastAPI, Anthropic SDK

---

## Week 5 — Memory & Retrieval-Augmented Generation
**Topics**
- Short-term vs long-term memory
- Embeddings and vector search
- RAG as a memory strategy
- Knowledge grounding and context management

**Papers**
- Lewis et al. (2020) — Retrieval-Augmented Generation 
- Packer et al. (2023) — MemGPT 

**Lab**
Build a RAG pipeline over a document corpus (e.g. course papers). Add persistent memory using ChromaDB. Compare agent answers with and without retrieval on factual questions.

**Tech Stack:** LangChain, ChromaDB, FAISS, OpenAI Embeddings

---

## Week 6 — Planning and Task Decomposition
**Topics**
- Task decomposition strategies
- Planning vs execution
- Hierarchical and sequential planners
- Failure recovery in plans

**Papers**
- Yao et al. (2023) — Tree of Thoughts 
- Wang et al. (2023) — Plan-and-Solve Prompting 

**Lab**
Give an agent a complex multi-step goal (e.g. "research a topic and write a structured report"). Implement a planner that decomposes it into subtasks, executes each, and handles failures by replanning.

**Tech Stack:** LangGraph, Anthropic SDK

---

## Week 7 — Multi-Agent Systems
**Topics**
- Role-based agents
- Agent communication and coordination
- Consensus, delegation, and conflict
- Swarm vs orchestrated architectures

**Papers**
- Park et al. (2023) — Generative Agents 
- Wu et al. (2023) — AutoGen 

**Lab**
Build a 3-agent pipeline: a Researcher, a Critic, and an Editor. Use AutoGen or CrewAI for orchestration. Observe how agents negotiate, correct each other, and converge on an output.

**Tech Stack:** AutoGen or CrewAI, Anthropic SDK

---

## Week 8 — Agent Frameworks & Architectures
**Topics**
- LangGraph, AutoGen, CrewAI in practice
- Framework vs custom agents
- Orchestration patterns
- Agent lifecycle management

**Lab**
Rebuild the Week 3 ReAct agent in LangGraph using a proper state graph. Then extend it with branching logic (e.g. error handling paths). Compare the graph-based approach to the manual loop.

**Tech Stack:** LangGraph, LangSmith (for tracing)

---

## Week 9 — Human-in-the-Loop (HITL)
**Topics**
- Approval flows and interrupt patterns
- When and how to escalate to humans
- Confidence thresholds and ambiguity handling
- HITL in regulated or high-stakes domains
- UX design for human–agent collaboration

**Papers / Resources**
- Amershi et al. (2019) — Guidelines for Human-AI Interaction 
- Anthropic (2024) — Responsible Scaling and Human Oversight 

**Lab**
Add a HITL interrupt to the Week 6 planner: the agent pauses and requests human approval before any "irreversible" action (e.g. sending an email, deleting a file). Implement approval via CLI, then a simple web UI.

**Tech Stack:** LangGraph (interrupt nodes), FastAPI, simple HTML frontend

---

## Week 10 — Computer Use & GUI Agents
**Topics**
- Browser and desktop automation agents
- Screen understanding and grounding
- GUI action spaces (click, type, scroll)
- Anthropic Computer Use, OpenAI Operator
- Risks and sandboxing for GUI agents

**Papers / Resources**
- Anthropic (2024) — Computer Use (Claude) 
- Deng et al. (2023) — Mind2Web 
- Zhou et al. (2023) — WebArena 
- He et al. (2024) — WebVoyager 

**Lab**
Build a browser agent using Playwright that can navigate a website, fill a form, and extract structured data. Then run the same task using Claude's Computer Use API. Compare reliability and control.

**Tech Stack:** Playwright, Anthropic Computer Use API, Docker (sandboxing)

---

## Week 11 — Safety, Alignment & Guardrails
**Topics**
- Prompt injection attacks
- Adversarial robustness in agentic pipelines
- Guardrails and output filtering
- Minimal footprint and safe action principles

**Papers**
- Perez & Ribeiro (2022) — Prompt Injection Attacks 
- Anthropic (2022) — Constitutional AI 
- Rebedea et al. (2023) — NeMo Guardrails 

**Lab**
Red-team your own agent: craft prompt injection attacks against the Week 3 or Week 6 agent and document what breaks. Then add guardrails (input validation, output filtering, action whitelisting) and re-test.

**Tech Stack:** Guardrails AI or custom filters, Anthropic SDK

---

## Week 12 — Evaluation of Agent Systems
**Topics**
- Metrics for agent performance
- Benchmarks (AgentBench, WebArena, SWE-bench)
- Reliability and failure mode analysis
- Evaluating multi-step reasoning chains

**Papers**
- Liu et al. (2023) — AgentBench 
- Yang et al. (2024) — SWE-bench 
- Xie et al. (2024) — OSWorld 

**Lab**
Design an evaluation harness for one of your prior agents. Define task success criteria, run 20+ trials, compute pass@k and failure breakdown. Optionally submit to a public leaderboard.

**Tech Stack:** Python, Weights & Biases, custom eval harness

---

## Week 13 — Observability, Debugging & Production
**Topics**
- Tracing and logging agent runs
- Debugging multi-step failures
- Infrastructure and deployment
- Cost optimization and latency

**Lab**
Instrument the Week 7 multi-agent system with full LangSmith tracing. Identify and fix a latency bottleneck. Deploy the agent as a REST API endpoint and load-test it.

**Tech Stack:** LangSmith, Arize Phoenix, FastAPI, Docker, Modal

---

## Week 14 — Frontiers in Agentic AI
**Topics**
- Self-improving and self-correcting agents
- Fully autonomous systems and open challenges
- Long-horizon task completion
- Ethical and societal implications
- Future research directions

**Lab**
Open-ended capstone: propose and prototype a novel agent application combining at least 3 concepts from the course (e.g. multi-agent + HITL + MCP). Present a 10-minute demo and a 2-page design doc.

**Tech Stack:** Student's choice
