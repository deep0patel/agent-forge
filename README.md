# 🔨 Agent Forge

> **The Universal Blueprint for Production-Ready AI Agent Systems**

Build sophisticated AI agents that run anywhere, connect to anything, and scale infinitely. Zero vendor lock-in. Maximum flexibility.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Go](https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white)](https://golang.org/)
[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-blue)](https://modelcontextprotocol.io)

---

## 🎯 What is Agent Forge?

Agent Forge is a **comprehensive master prompt and architecture blueprint** that enables any AI coding assistant (Claude Code, GitHub Copilot, Cursor, etc.) to generate a complete, production-ready agent system tailored to your needs.

Think of it as the "create-react-app" for AI agents - but infinitely more flexible.

### ✨ Key Features

- 🌍 **Universal**: Works with any language, any LLM, any cloud platform
- 🔌 **MCP Native**: Full Model Context Protocol support built-in
- 🧠 **Memory-Enabled**: Three-layer memory system for continuous learning
- 🤝 **Multi-Agent**: Swarm orchestration for complex tasks
- 🔒 **Production-Ready**: Error handling, observability, security out-of-the-box
- 📦 **Zero Lock-In**: Swap any component (LLM, database, cloud) without refactoring
- 📚 **Self-Documenting**: Auto-generates comprehensive guides and ADRs

---

## 🚀 Quick Start

### Option 1: Use with Claude Code (Recommended)

```bash
# Install Claude Code CLI
npm install -g @anthropic/claude-code

# Create your agent
claude-code create my-agent --prompt agent-forge.md

# Follow the interactive prompts to configure your stack
```

### Option 2: Use with Any AI Assistant

1. Copy the master prompt from `agent-forge-master-prompt.md`
2. Provide your configuration:

```yaml
# config.yaml
project:
  name: "my-coding-agent"
  use_case: "code generation"
  
tech_stack:
  language: "typescript"  # or python, go, rust
  
deployment:
  target: "docker"  # or aws-lambda, kubernetes, etc.
  
llm_strategy:
  primary_provider: "anthropic"
  routing: "balanced"
```

3. Paste both into your AI assistant
4. Get a complete, runnable agent system in minutes

### Option 3: Manual Implementation

See our [Implementation Guide](./docs/IMPLEMENTATION.md) for step-by-step instructions.

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    USER INTERFACE                        │
│          (CLI, API, Web UI, IDE Plugin)                 │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│                   AGENT ORCHESTRATOR                     │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐ │
│  │   Task       │  │   Memory     │  │   Learning   │ │
│  │   Router     │  │   System     │  │   Engine     │ │
│  └──────────────┘  └──────────────┘  └──────────────┘ │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│                    MCP CLIENT LAYER                      │
│  (Model Context Protocol - Universal Tool Interface)    │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│                  EXECUTION ENGINES                       │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐  │
│  │   LLM    │ │  Tools   │ │  Swarm   │ │ External │  │
│  │  Router  │ │ Executor │ │  Coord   │ │   APIs   │  │
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘  │
└─────────────────────────────────────────────────────────┘
```

**Three-Layer Memory System**:
1. **Episodic Memory**: Conversation history with semantic search
2. **Reflexion Memory**: Success/failure patterns for learning
3. **Skill Library**: Consolidated, reusable patterns

---

## 💡 Use Cases

### 🔧 Code Generation Agent
Generate complete applications, write tests, review code, refactor legacy systems.

```yaml
use_case: "code generation"
tools: ["filesystem", "github", "code-execution"]
specialization: "full-stack development"
```

### 📊 Data Analysis Agent
Process datasets, generate insights, create visualizations, build dashboards.

```yaml
use_case: "data analysis"
tools: ["filesystem", "database", "python-execution"]
specialization: "data science"
```

### 🤖 DevOps Automation Agent
Deploy applications, manage infrastructure, monitor systems, handle incidents.

```yaml
use_case: "devops automation"
tools: ["kubernetes", "terraform", "aws-cli"]
specialization: "cloud infrastructure"
```

### 🔍 Research Assistant Agent
Gather information, synthesize findings, write reports, track sources.

```yaml
use_case: "research"
tools: ["web-search", "pdf-reader", "database"]
specialization: "research and analysis"
```

---

## 🎓 Examples

### Basic Code Generation

```typescript
import { Agent } from 'agent-forge';

const agent = new Agent({
  llm: { provider: 'anthropic', model: 'claude-sonnet-4' },
  tools: ['read_file', 'write_file', 'execute_code'],
  memory: { backend: 'sqlite' }
});

const result = await agent.run(
  "Create a REST API for a todo app with TypeScript and Express"
);

console.log(result);
```

### Multi-Agent Swarm

```typescript
import { SwarmOrchestrator } from 'agent-forge/swarm';

const swarm = new SwarmOrchestrator({
  queen: { model: 'claude-sonnet-4' },
  workers: {
    coder: { specialization: 'code-generation' },
    tester: { specialization: 'testing' },
    reviewer: { specialization: 'code-review' }
  }
});

const result = await swarm.execute(
  "Build a full-stack web app with authentication and database"
);
```

### With Memory & Learning

```typescript
const agent = new Agent({
  llm: { provider: 'anthropic' },
  memory: {
    backend: 'postgres',
    vectorDB: 'pgvector',
    enableReflexion: true,
    enableSkillLibrary: true
  }
});

// First run - agent learns
await agent.run("Create a Python Flask API");

// Future runs - agent applies learned patterns
await agent.run("Create a FastAPI service");
// ✅ Agent reuses patterns from Flask experience
```

---

## 🔌 MCP Integration

Agent Forge is MCP-native. Connect to any MCP server:

```yaml
mcp:
  servers:
    # Filesystem operations
    - name: "filesystem"
      command: "npx"
      args: ["-y", "@modelcontextprotocol/server-filesystem", "/workspace"]
    
    # GitHub integration
    - name: "github"
      command: "npx"
      args: ["-y", "@modelcontextprotocol/server-github"]
      env:
        GITHUB_TOKEN: "${GITHUB_TOKEN}"
    
    # Web search
    - name: "brave-search"
      command: "npx"
      args: ["-y", "@modelcontextprotocol/server-brave-search"]
      env:
        BRAVE_API_KEY: "${BRAVE_API_KEY}"
    
    # Your custom server
    - name: "custom-tools"
      command: "node"
      args: ["./servers/custom.js"]
```

**100+ Tools Available**: File operations, code execution, version control, web APIs, databases, and more.

---

## 🎯 Supported Stacks

### Languages
- ✅ **TypeScript/Node.js** (Best ecosystem, MCP native)
- ✅ **Python** (Best ML libraries, LangChain integration)
- ✅ **Go** (Lowest latency, easiest deployment)
- ✅ **Rust** (Maximum performance, WASM compilation)
- ✅ **Java** (Enterprise-grade)

### LLM Providers
- 🤖 **Anthropic**: Claude Sonnet 4, Haiku 4, Opus 4
- 🧠 **OpenAI**: GPT-4o, o1, o3-mini
- 🌟 **Google**: Gemini 2.5 Pro, Flash
- 🔓 **Open Source**: Qwen3 Coder, DeepSeek R1, CodeStral
- 🏠 **Local**: Ollama, LM Studio, vLLM

### Deployment Targets
- 🐳 **Docker** & Docker Compose
- ☁️ **AWS**: Lambda, ECS, EC2
- 🌩️ **GCP**: Cloud Functions, Cloud Run, GKE
- 🔷 **Azure**: Functions, Container Apps, AKS
- ⚡ **Edge**: Cloudflare Workers, Vercel Edge
- 🏠 **Self-Hosted**: Any VPS or on-premise

### Memory Backends
- 💾 **SQLite** (Local development)
- 🐘 **PostgreSQL + pgvector** (Production)
- ⚡ **Redis/Valkey** (Distributed)
- 🔍 **Qdrant, Weaviate, Chroma** (Vector search)
- ☁️ **DynamoDB, Firestore, MongoDB Atlas** (Serverless)

---

## 📊 Benchmarks

Agent Forge-generated agents achieve industry-competitive performance:

| Metric | Target | Best in Class |
|--------|--------|---------------|
| SWE-Bench Score | 70%+ | 72.7% (Claude 4) |
| HumanEval Pass@1 | 90%+ | 92% (GPT-4) |
| Token Efficiency | 30%+ reduction | Via smart routing |
| Memory Retrieval | <100ms | With pgvector |
| Tool Success Rate | 95%+ | With retry logic |
| Parallel Speedup | 3-5x | Multi-agent swarm |

---

## 📚 Documentation

- **[Quick Start Guide](./docs/QUICK_START.md)** - Get running in 5 minutes
- **[Architecture Guide](./docs/ARCHITECTURE.md)** - Deep dive into system design
- **[Implementation Guide](./docs/IMPLEMENTATION.md)** - Step-by-step build instructions
- **[MCP Integration](./docs/MCP_INTEGRATION.md)** - Tool connectivity guide
- **[Extension Guide](./docs/EXTENDING.md)** - Add your own tools and providers
- **[Deployment Guide](./docs/DEPLOYMENT.md)** - Production deployment options
- **[API Reference](./docs/API_REFERENCE.md)** - Complete API documentation
- **[Troubleshooting](./docs/TROUBLESHOOTING.md)** - Common issues and solutions
- **[ADRs](./docs/ADRs/)** - Architecture Decision Records

---

## 🛠️ Development

### Prerequisites

- Node.js 18+ / Python 3.11+ / Go 1.21+ (depending on your stack)
- Docker (optional, for containerized deployment)
- An LLM API key (Anthropic, OpenAI, etc.)

### Local Development

```bash
# Clone the repository
git clone https://github.com/yourusername/agent-forge.git
cd agent-forge

# Install dependencies (for TypeScript)
npm install

# Copy environment template
cp .env.example .env
# Edit .env with your API keys

# Run locally
npm run dev

# Run tests
npm test

# Run benchmarks
npm run benchmark
```

### Docker Development

```bash
# Start all services
docker-compose up

# Your agent is now running at http://localhost:3000
```

---

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

### Ways to Contribute

- 🐛 **Report bugs** via GitHub Issues
- 💡 **Suggest features** via Discussions
- 📝 **Improve documentation**
- 🔧 **Add new tool integrations**
- 🎨 **Create example implementations**
- 🧪 **Write tests and benchmarks**

---

## 🌟 Inspiration & Credits

Agent Forge synthesizes best practices from:

- **[agentic-flow](https://github.com/ruvnet/agentic-flow)** - Memory systems, SONA learning
- **[claude-flow](https://github.com/example/claude-flow)** - Hive-mind architecture
- **[Amp Code](https://ampcode.com/how-to-build-an-agent)** - Elegant simplicity
- **[Model Context Protocol](https://modelcontextprotocol.io)** - Universal tool interface
- **OpenAI Codex** - Async workflows
- **Cursor, Continue** - IDE integration patterns

Standing on the shoulders of giants. 🙏

---

## 📄 License

MIT License - see [LICENSE](./LICENSE) for details.

---

## 🔗 Links

- **Documentation**: [https://agent-forge.dev](https://agent-forge.dev)
- **GitHub**: [https://github.com/yourusername/agent-forge](https://github.com/yourusername/agent-forge)
- **Discord**: [Join our community](https://discord.gg/agent-forge)
- **Twitter**: [@AgentForge](https://twitter.com/agentforge)

---

## ⭐ Star History

If Agent Forge helped you build amazing agents, give us a star! ⭐

[![Star History Chart](https://api.star-history.com/svg?repos=yourusername/agent-forge&type=Date)](https://star-history.com/#yourusername/agent-forge&Date)

---

## 🚀 Ready to Build?

```bash
# Start your agent journey today
npx agent-forge create my-first-agent

# Or use with your favorite AI assistant
cat agent-forge-master-prompt.md | claude-code
```

**Build agents that matter. Build with Agent Forge.** 🔨

---

<p align="center">
  Made with ❤️ by developers, for developers
</p>

<p align="center">
  <a href="#-what-is-agent-forge">What is it?</a> •
  <a href="#-quick-start">Quick Start</a> •
  <a href="#-examples">Examples</a> •
  <a href="#-documentation">Docs</a> •
  <a href="#-contributing">Contributing</a>
</p>