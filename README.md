<picture class="github-only">
  <source media="(prefers-color-scheme: light)" srcset="https://langchain-ai.github.io/langgraph/static/wordmark_dark.svg">
  <source media="(prefers-color-scheme: dark)" srcset="https://langchain-ai.github.io/langgraph/static/wordmark_light.svg">
  <img alt="LangGraph Logo" src="https://langchain-ai.github.io/langgraph/static/wordmark_dark.svg" width="80%">
</picture>

<div>
<br>
</div>

[![Version](https://img.shields.io/pypi/v/langgraph.svg)](https://pypi.org/project/langgraph/)
[![Downloads](https://static.pepy.tech/badge/langgraph/month)](https://pepy.tech/project/langgraph)
[![Open Issues](https://img.shields.io/github/issues-raw/langchain-ai/langgraph)](https://github.com/langchain-ai/langgraph/issues)
[![Docs](https://img.shields.io/badge/docs-latest-blue)](https://langchain-ai.github.io/langgraph/)

## 🧭 MAOS v1 Governance (Activ8-AI Fork)

This fork operates under MAOS v1 (Modular Automation Operating System) governance framework, which establishes:

- **Tier 3 Repository Classification**: Full governance controls with automated agent workflows
- **Charter Compliance**: All changes must align with Charter Standards for security, modularity, and provider-agnostic design
- **Fail-Closed Enforcement**: Required governance checks must pass before merge
- **Human Authority**: All merges require explicit human approval
- **Audit Trail**: Comprehensive logging and compliance tracking

### Fork-Specific Governance

This is an Activ8-AI maintained fork of [LangGraph](https://github.com/langchain-ai/langgraph).

**Upstream Synchronization**:
- Regular syncs with upstream LangGraph repository
- Activ8-AI specific modifications tracked separately
- Governance requirements apply to Activ8-AI changes only

**Contribution Guidelines**:
- Upstream contributions should be made to the original LangGraph repository
- Activ8-AI specific features require governance approval
- See main repository [Activ8-AI/mcp](https://github.com/Activ8-AI/mcp) for governance details

For complete governance documentation, see:
- **Main Repository**: [Activ8-AI/mcp](https://github.com/Activ8-AI/mcp) - Primary governance standards
- **Upstream**: [langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) - Original project
- **Documentation**: [langchain-ai.github.io/langgraph](https://langchain-ai.github.io/langgraph) - Official docs
- **LangChain**: [LangChain AI](https://www.langchain.com/) - Parent framework

### High-Risk Powers

This agent framework has specific governance requirements:

- **Agent Orchestration**: Low-level framework for stateful agent workflows
- **LLM Integration**: Direct access to language models (Anthropic, OpenAI, etc.)
- **Tool Execution**: Dynamic tool calling and external system integration
- **State Management**: Persistent state with long-term memory across sessions
- **Durable Execution**: Automatic resume from failures with state persistence
- **Human-in-the-Loop**: Agent state inspection and modification capabilities
- **Multi-Agent Systems**: Coordinated agent collaboration and communication
- **Custom Workflows**: Unrestricted workflow architecture and control flow
- **External APIs**: Agent access to external services and data sources

All high-risk operations are:
- Gated behind required human approval
- Logged for audit compliance
- Subject to automated security scanning
- Governed by principle of least privilege
- Require secure credential management

### Security Notes

- **LLM API Keys**: Never commit API keys for language model providers
- **Tool Permissions**: Review and limit tools accessible to agents
- **State Persistence**: Secure storage for agent state and memory
- **Human Oversight**: Implement human-in-the-loop for critical decisions
- **External Access**: Validate and sanitize all external API interactions
- **Prompt Injection**: Protect against prompt injection in agent workflows
- **Credential Management**: Use environment variables for all API credentials
- **Agent Boundaries**: Define clear operational boundaries for agents

Trusted by companies shaping the future of agents – including Klarna, Replit, Elastic, and more – LangGraph is a low-level orchestration framework for building, managing, and deploying long-running, stateful agents.

## Get started

Install LangGraph:

```
pip install -U langgraph
```

Then, create an agent [using prebuilt components](https://langchain-ai.github.io/langgraph/agents/agents/):

```python
# pip install -qU "langchain[anthropic]" to call the model

from langgraph.prebuilt import create_react_agent

def get_weather(city: str) -> str:
    """Get weather for a given city."""
    return f"It's always sunny in {city}!"

agent = create_react_agent(
    model="anthropic:claude-3-7-sonnet-latest",
    tools=[get_weather],
    prompt="You are a helpful assistant"
)

# Run the agent
agent.invoke(
    {"messages": [{"role": "user", "content": "what is the weather in sf"}]}
)
```

For more information, see the [Quickstart](https://langchain-ai.github.io/langgraph/agents/agents/). Or, to learn how to build an [agent workflow](https://langchain-ai.github.io/langgraph/concepts/low_level/) with a customizable architecture, long-term memory, and other complex task handling, see the [LangGraph basics tutorials](https://langchain-ai.github.io/langgraph/tutorials/get-started/1-build-basic-chatbot/).

## Core benefits

LangGraph provides low-level supporting infrastructure for *any* long-running, stateful workflow or agent. LangGraph does not abstract prompts or architecture, and provides the following central benefits:

- [Durable execution](https://langchain-ai.github.io/langgraph/concepts/durable_execution/): Build agents that persist through failures and can run for extended periods, automatically resuming from exactly where they left off.
- [Human-in-the-loop](https://langchain-ai.github.io/langgraph/concepts/human_in_the_loop/): Seamlessly incorporate human oversight by inspecting and modifying agent state at any point during execution.
- [Comprehensive memory](https://langchain-ai.github.io/langgraph/concepts/memory/): Create truly stateful agents with both short-term working memory for ongoing reasoning and long-term persistent memory across sessions.
- [Debugging with LangSmith](http://www.langchain.com/langsmith): Gain deep visibility into complex agent behavior with visualization tools that trace execution paths, capture state transitions, and provide detailed runtime metrics.
- [Production-ready deployment](https://langchain-ai.github.io/langgraph/concepts/deployment_options/): Deploy sophisticated agent systems confidently with scalable infrastructure designed to handle the unique challenges of stateful, long-running workflows.

## LangGraph’s ecosystem

While LangGraph can be used standalone, it also integrates seamlessly with any LangChain product, giving developers a full suite of tools for building agents. To improve your LLM application development, pair LangGraph with:

- [LangSmith](http://www.langchain.com/langsmith) — Helpful for agent evals and observability. Debug poor-performing LLM app runs, evaluate agent trajectories, gain visibility in production, and improve performance over time.
- [LangSmith Deployment](https://langchain-ai.github.io/langgraph/concepts/langgraph_platform/) — Deploy and scale agents effortlessly with a purpose-built deployment platform for long running, stateful workflows. Discover, reuse, configure, and share agents across teams — and iterate quickly with visual prototyping in [LangGraph Studio](https://langchain-ai.github.io/langgraph/concepts/langgraph_studio/).
- [LangChain](https://python.langchain.com/docs/introduction/) – Provides integrations and composable components to streamline LLM application development.

> [!NOTE]
> Looking for the JS version of LangGraph? See the [JS repo](https://github.com/langchain-ai/langgraphjs) and the [JS docs](https://langchain-ai.github.io/langgraphjs/).

## Additional resources

- [Guides](https://langchain-ai.github.io/langgraph/guides/): Quick, actionable code snippets for topics such as streaming, adding memory & persistence, and design patterns (e.g. branching, subgraphs, etc.).
- [Reference](https://langchain-ai.github.io/langgraph/reference/graphs/): Detailed reference on core classes, methods, how to use the graph and checkpointing APIs, and higher-level prebuilt components.
- [Examples](https://langchain-ai.github.io/langgraph/examples/): Guided examples on getting started with LangGraph.
- [LangChain Forum](https://forum.langchain.com/): Connect with the community and share all of your technical questions, ideas, and feedback.
- [LangChain Academy](https://academy.langchain.com/courses/intro-to-langgraph): Learn the basics of LangGraph in our free, structured course.
- [Templates](https://langchain-ai.github.io/langgraph/concepts/template_applications/): Pre-built reference apps for common agentic workflows (e.g. ReAct agent, memory, retrieval etc.) that can be cloned and adapted.
- [Case studies](https://www.langchain.com/built-with-langgraph): Hear how industry leaders use LangGraph to ship AI applications at scale.

## Acknowledgements

LangGraph is inspired by [Pregel](https://research.google/pubs/pub37252/) and [Apache Beam](https://beam.apache.org/). The public interface draws inspiration from [NetworkX](https://networkx.org/documentation/latest/). LangGraph is built by LangChain Inc, the creators of LangChain, but can be used without LangChain.