# 🗺️ HiveLLM Ecosystem Map

## 🎯 Overview

HiveLLM is a comprehensive multi-agent ecosystem built around autonomous AI governance and collaborative development. The ecosystem consists of specialized components designed to work together through unified protocols, providing infrastructure for persistent memory, communication, task management, and agent orchestration.

---

## 📊 Core Components

### 🏛️ **gov** - Governance & Decision Making
**Location**: `./gov/`  
**Technology**: Node.js, TypeScript, SQLite  
**Status**: 🔄 Active Development (Multi-Agent Dashboard Pending)

**Purpose**: Central governance hub with all organizational processes and decision-making infrastructure.

**Key Features**:
- BIP (Blockchain Improvement Proposal) specifications
- Democratic voting and consensus systems
- Proposal management and tracking
- Meeting minutes and decision records
- Team structure and guidelines
- Metrics and analytics

**Current State**:
- Operational governance dashboard
- Semi-manual processes being automated
- Foundation for future unified automated system
- Multiple ongoing demands requiring structural improvements

**Next Steps**:
- Dashboard rebuild for multi-agent management
- Full automation of governance workflows
- Integration with agent framework for autonomous governance

---

### 🧠 **vectorizer** - Persistent Memory & Vector Database
**Location**: `./vectorizer/`  
**Technology**: Rust  
**Status**: ✅ Operational (MCP & REST Functional)

**Purpose**: Vector database serving as persistent memory for AI agents, preventing context loss across multi-agent operations.

**Key Features**:
- MCP (Model Context Protocol) integration
- REST API for flexible access
- High-performance vector search
- HNSW indexing
- Real-time embedding generation
- Workspace vectorization

**Current Capabilities**:
- ✅ MCP server operational
- ✅ REST API functional
- ✅ Vector storage and retrieval
- ✅ Multi-modal embedding support

**Next Steps** (Roadmap):
- 🔄 Plugin system for extensibility
- 🔄 File format conversion (PDF, DOCX, Excel → Text)
- 🔄 Data normalization for memory optimization
- 🔄 Clustering and semantic grouping
- 🔄 Full GPU VRAM integration
- 🔄 Agent integration modules

**Use Cases**:
- Persistent context across agent sessions
- Knowledge base for agent teams
- Document indexing and semantic search
- Cross-agent memory sharing

---

### 🌐 **UMICP** - Universal Multi-Agent Communication Protocol
**Location**: `./umicp/`  
**Technology**: C++17 core, Multi-language bindings  
**Status**: ✅ Advanced Implementation (BIP-05)

**Purpose**: High-efficiency multi-language communication protocol designed for agent interoperability.

**Key Features**:
- WebSocket support for real-time communication
- StreamableHTTP for efficient data transfer
- Multi-language bindings (TypeScript, Python, Rust, Go, Java, PHP, etc.)
- High-performance C++ core
- Encryption and compression built-in
- Load balancing and routing

**Current Capabilities**:
- ✅ WebSocket server/client
- ✅ StreamableHTTP implementation
- ✅ Multi-language bindings
- ✅ Core protocol complete

**Use Cases**:
- Agent-to-agent communication
- Service mesh for microservices
- Real-time event streaming
- Cluster-wide coordination

**Architecture**:
```
┌─────────────┐     UMICP     ┌─────────────┐
│   Agent A   │◄─────────────►│   Agent B   │
└─────────────┘               └─────────────┘
       │                             │
       │         UMICP Network       │
       │                             │
       ▼                             ▼
┌─────────────┐               ┌─────────────┐
│  Vectorizer │               │  Task Queue │
└─────────────┘               └─────────────┘
```

---

### 🎤 **Voxa** - Voice Interaction Assistant
**Location**: `./voxa/`  
**Technology**: Python (Models: Local STT/TTS)  
**Status**: 🔄 In Development

**Purpose**: Personal AI assistant with voice interaction capabilities for desktop and mobile platforms.

**Key Features**:
- Local speech-to-text (STT) models
- Local text-to-speech (TTS) models
- UMICP integration for agent cluster access
- Vectorizer integration for knowledge access
- Desktop and mobile support
- Agent orchestration capabilities
- Multi-modal interaction

**Architecture**:
```
Human ◄──Voice──► Voxa ◄──UMICP──► Agent Cluster
                    │
                    └──► Vectorizer (Memory)
                    └──► Task Queue (Tasks)
```

**Planned Capabilities**:
- 🔄 Voice command processing
- 🔄 Natural language understanding
- 🔄 Agent task delegation
- 🔄 Context-aware responses
- 🔄 Desktop application
- 🔄 Mobile application
- 🔄 Continuous interaction mode

---

### 📋 **Task Queue** - Multi-Agent Task Orchestration
**Location**: `./task-queue/`  
**Technology**: Rust  
**Status**: ✅ Operational (Improvements Planned)

**Purpose**: Task organization and workflow management system for coordinating multiple agents, combining Trello-like boards with organizational queues and pre-defined prompt pipelines.

**Key Features**:
- Task creation and tracking
- Multi-agent task assignment
- Pre-defined prompt pipelines for task stages
- Trello-style board organization
- Queue-based task distribution
- Task dependencies and workflows
- Dashboard visualization

**Current Capabilities**:
- ✅ Task queue management
- ✅ Basic workflow orchestration
- ✅ Dashboard interface
- ✅ Task prioritization

**Next Steps**:
- 🔄 Review agent integration
- 🔄 Custom pipeline creation
- 🔄 Quality control workflows
- 🔄 Advanced agent coordination
- 🔄 Implementation validation

**Use Cases**:
- Multi-agent development workflows
- Quality assurance pipelines
- Automated code review
- Task decomposition and distribution
- Progress tracking and reporting

**Workflow Example**:
```
Task Created → Planning Agent → Implementation Agent → Review Agent → Validation → Complete
     │              │                   │                    │           │
     └──────────────┴───────────────────┴────────────────────┴───────────┘
                           Task Queue Orchestration
```

---

### 🔌 **Gateway** - MCP Tools Unification & Permission Management
**Location**: `./gateway/`  
**Technology**: TypeScript, Node.js  
**Status**: 🔄 In Development

**Purpose**: Unified gateway for MCP (Model Context Protocol) tools with enterprise-grade permission management and customization capabilities.

**Key Features**:
- MCP tool aggregation and unification
- Permission-based access control
- Enterprise tool management
- Integration customization
- Similar to StormMCP approach
- Multi-tenant support

**Architecture**:
```
┌─────────────┐
│  Agent/LLM  │
└──────┬──────┘
       │
       ▼
┌─────────────┐      ┌──────────────┐
│   Gateway   │─────►│ MCP Tool A   │
│  (Auth &    │─────►│ MCP Tool B   │
│ Permissions)│─────►│ MCP Tool C   │
└─────────────┘      └──────────────┘
```

**Use Cases**:
- Enterprise tool access management
- Secure multi-tenant environments
- Centralized MCP tool catalog
- Permission auditing and compliance
- Custom tool integration

---

### 🤖 **Agent Framework** - Multi-Language Agent Development Framework
**Location**: `./agent-framework/`  
**Technology**: TypeScript (Multi-language planned)  
**Status**: 🔄 Active Development

**Purpose**: Standardized framework for creating specialized AI agents with automatic protocol integration and multi-LLM support.

**Key Features**:
- Schema-based agent definition
- Handler-based event system
- Automatic MCP integration
- Automatic REST integration
- Automatic UMICP integration
- Multi-LLM adapters (API and local models)
- Similar architecture to CrewAI
- Simple agent generation from templates

**Agent Structure**:
```typescript
// Simplified agent creation
const agent = new Agent({
  name: "CodeReviewer",
  schema: reviewSchema,
  handlers: {
    onTask: reviewHandler,
    onComplete: notifyHandler
  },
  integrations: ["mcp", "rest", "umicp"],
  llm: {
    provider: "openai",
    model: "gpt-4"
  }
});
```

**Automatic Integrations**:
- ✅ MCP server generation from schema
- ✅ REST API generation from schema
- ✅ UMICP protocol support
- ✅ LLM adapter layer (OpenAI, Anthropic, Local, etc.)

**Use Cases**:
- Rapid agent development
- Specialized task agents
- Agent team composition
- Standardized agent communication
- Multi-agent orchestration

---

### 8. 🔄 **Synap** - In-Memory Data Infrastructure
**Location**: `./synap/`  
**Technology**: Rust (Edition 2024)  
**Status**: ✅ Operational (Production Ready v0.3.0-rc)

**Purpose**: High-performance in-memory data infrastructure combining Redis, RabbitMQ, and Kafka features into a unified platform.

**Key Features**:
- 💾 **Memory Key-Value Store**: Radix-tree based with O(k) lookup (87ns GET operations)
- #️⃣ **Hash Data Structure**: Redis-compatible HSET, HGET operations
- 📋 **List Data Structure**: LPUSH, RPOP, LRANGE support
- 🔷 **Set Data Structure**: SADD, SREM, SINTER, SUNION operations
- 📨 **Acknowledgment Queues**: RabbitMQ-style message queues with delivery guarantees
- 📡 **Event Streams**: Kafka-style partitioned topics with consumer groups
- 🔔 **Pub/Sub Messaging**: Topic-based publish/subscribe with wildcard support
- 🔄 **Master-Slave Replication**: Production-ready async replication with auto-reconnect
- 💾 **Persistence**: WAL + Snapshots for durability (PC/EL consistency model)

**Architecture**:
```
┌─────────────────────────────────────────────────────────┐
│                     Synap Server                        │
├─────────────────────────────────────────────────────────┤
│  StreamableHTTP/WebSocket Protocol Layer               │
├─────────────────────────────────────────────────────────┤
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐  │
│  │ Key-Value│ │  Queue   │ │  Event   │ │  Pub/Sub │  │
│  │  Store   │ │  System  │ │  Stream  │ │          │  │
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘  │
├─────────────────────────────────────────────────────────┤
│            Replication Log (Append-Only)                │
├─────────────────────────────────────────────────────────┤
│  Master Node              Replica Nodes (Read-Only)     │
└─────────────────────────────────────────────────────────┘
```

**Current Capabilities**:
- ✅ 10M+ ops/sec sequential writes
- ✅ 92MB for 1M keys (54% reduction vs baseline)
- ✅ 99.30% test coverage (456/456 tests passing)
- ✅ MCP and UMICP protocol support
- ✅ TypeScript, Python, and Rust SDKs

**Next Steps**:
- 🔄 Advanced monitoring (Prometheus integration)
- 🔄 Clustering and sharding support
- 🔄 GUI Dashboard for management
- 🔄 Distribution packages

**Use Cases**:
- Real-time agent coordination
- Task queuing for multi-agent workflows
- Event streaming for telemetry
- Session state management
- Cache layer for high-speed data access

---

### ⚡ **HiveGPU** - GPU Computation Framework
**Location**: `./hivegpu/` (Planned)  
**Technology**: C++ with Rust FFI  
**Status**: 🔜 Planned Component

**Purpose**: High-performance GPU computation framework for vector operations and matrix processing with VRAM buffer management.

**Key Features**:
- VRAM buffer allocation and management
- HNSW (Hierarchical Navigable Small World) matrix processing
- Pre-allocated data structures for GPU
- Multi-backend support:
  - CUDA (NVIDIA)
  - Vulkan (Cross-platform)
  - Metal (Apple)
- Rust library bindings
- Zero-copy operations where possible

**Architecture**:
```
┌─────────────────┐
│  Rust/C++ Core  │
└────────┬────────┘
         │
    ┌────┴────┐
    │  GPU    │
    │ Backend │
    └────┬────┘
         │
  ┌──────┴──────┐
  │   VRAM      │
  │  Buffers    │
  │  HNSW Data  │
  └─────────────┘
```

**Planned Integration**:
- 🔜 Vectorizer GPU acceleration
- 🔜 HNSW index on GPU
- 🔜 Batch vector operations
- 🔜 Real-time embedding generation
- 🔜 Optimized similarity search

**Use Cases**:
- Accelerated vector search
- Large-scale embedding generation
- Real-time semantic search
- GPU-optimized HNSW operations
- High-throughput vector operations

---

### 🔄 **Transmutation** - Document Conversion Engine
**Location**: `./transmutation/`  
**Technology**: Rust (Pure Rust + Optional External Tools)  
**Status**: ✅ Operational (v0.1.1 Production Ready)

**Purpose**: High-performance document conversion engine for AI/LLM embeddings, 98x faster than Docling.

**Key Features**:
- **PDF Conversion**: Fast mode (80% similarity) & Precision mode
- **Office Formats**: DOCX, XLSX, PPTX (Pure Rust, 148-1639 pg/s)
- **Web Formats**: HTML/XML (Pure Rust, 2110-2353 pg/s)
- **Image OCR**: Tesseract integration (88x faster than Docling)
- **Audio/Video**: Whisper transcription via FFmpeg
- **Archives**: ZIP, TAR, GZ support (1864 pg/s)
- **Windows MSI Installer**: Professional distribution tools

**Architecture**:
```
┌──────────────────────────────────────────────────┐
│         Transmutation Converter                  │
├──────────────────────────────────────────────────┤
│  Pure Rust Core (PDF, Office, HTML, XML, ZIP)   │
├──────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌──────────┐│
│  │   OCR       │  │   Audio     │  │  Future  ││
│  │ (Tesseract) │  │  (Whisper)  │  │  (C++ FFI)││
│  └─────────────┘  └─────────────┘  └──────────┘│
└──────────────────────────────────────────────────┘
           │
           ▼
    Markdown/Images/JSON
           │
           ▼
      Vectorizer
```

**Current Capabilities**:
- ✅ 11 document formats (8 production, 2 beta)
- ✅ 98x faster than Docling (0.37s vs 35s avg)
- ✅ 80% similarity (Fast mode), 95%+ planned (Precision with C++ FFI)
- ✅ 50MB memory footprint vs 2-3GB for Docling
- ✅ Zero runtime dependencies (core features)

**Next Steps**:
- 🔄 C++ FFI integration for 95%+ similarity
- 🔄 Python and TypeScript bindings
- 🔄 Performance optimizations
- 🔄 v1.0.0 release

**Use Cases**:
- RAG system document ingestion
- Document archive migration
- Legal document processing
- Academic paper analysis
- Data extraction from spreadsheets

---

### 🧠 **Nexus** - Graph Database with Vector Search
**Location**: `./nexus/`  
**Technology**: Rust (Edition 2024)  
**Status**: 🔄 Active Development (MVP Phase)

**Purpose**: Property graph database with native vector search for RAG applications requiring semantic similarity and graph traversal.

**Key Features**:
- **Property Graph Model**: Nodes with labels, relationships with types
- **Cypher Subset**: Familiar query language (80% of common use cases)
- **Neo4j-Inspired Storage**: Fixed-size record stores (32B nodes, 48B relationships)
- **O(1) Traversal**: Doubly-linked adjacency lists
- **ACID Transactions**: WAL + MVCC for durability
- **Native KNN**: HNSW indexes per label for vector search
- **Hybrid Queries**: Combine vector similarity with graph traversal

**Architecture**:
```
┌──────────────────────────────────────────────────────────┐
│                     REST/HTTP API                         │
│       POST /cypher • POST /knn_traverse • POST /ingest   │
└───────────────────────┬──────────────────────────────────┘
                        │
┌───────────────────────┴──────────────────────────────────┐
│                  Cypher Executor                          │
│        Pattern Match • Expand • Filter • Project         │
│         Heuristic Cost-Based Query Planner               │
└───────────────────────┬──────────────────────────────────┘
                        │
┌───────────────────────┴──────────────────────────────────┐
│            Transaction Layer (MVCC)                       │
│      Epoch-Based Snapshots • Single-Writer Locking       │
└───────────────────────┬──────────────────────────────────┘
                        │
┌───────────────────────┴──────────────────────────────────┐
│                   Index Layer                             │
│   Label Bitmap • B-tree (V1) • Full-Text (V1) • KNN     │
│   RoaringBitmap  •  Tantivy  •  HNSW (hnsw_rs)          │
└───────────────────────┬──────────────────────────────────┘
                        │
┌───────────────────────┴──────────────────────────────────┐
│                  Storage Layer                            │
│  Catalog (LMDB) • WAL • Record Stores • Page Cache      │
│  Label/Type/Key Mappings  •  Durability  •  Memory Mgmt │
└──────────────────────────────────────────────────────────┘
```

**Current Capabilities**:
- ✅ Architecture documentation complete
- ✅ Project scaffolding (Rust edition 2024)
- ✅ REST API framework (Axum)
- 🔄 Storage layer implementation
- 🔄 Basic Cypher executor

**Next Steps**:
- 🔄 Complete MVP storage layer
- 🔄 Basic Cypher query support
- 🔄 KNN vector search integration
- 🔄 Integration tests
- 🔄 Desktop GUI (Electron)

**Use Cases**:
- RAG with semantic + graph traversal
- Recommendation systems
- Knowledge graphs with embeddings
- Document networks with citation analysis
- Social networks with similarity search

---

### 🧬 **Reasoning** - Multi-Turn LLM Reasoning Engine
**Location**: `./ide/reasoning/`  
**Technology**: Rust (Edition 2024)  
**Status**: ✅ Operational (Production Ready)

**Purpose**: Local LLM inference with CUDA acceleration and advanced multi-turn reasoning capabilities.

**Key Features**:
- **Native Candle Engines**: Phi-3, Mistral, Qwen, Gemma
- **CUDA GPU Acceleration**: 5-36x speedup over CPU
- **MCP Integration**: Tool discovery and execution
- **Multi-Turn Reasoning**: DeepSeek integration for complex tasks
- **Automatic Prompt Compression**: 50% token reduction
- **Guardrails System**: Tool call validation
- **Hybrid Approaches**: Native + API combinations

**Architecture**:
```
┌─────────────────────────────────────────────┐
│         Reasoning Engine                     │
├─────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐        │
│  │    Native    │  │     API      │        │
│  │   Engines    │  │   Engines    │        │
│  │  (Candle)    │  │  (DeepSeek)  │        │
│  └──────────────┘  └──────────────┘        │
├─────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐        │
│  │     MCP      │  │  Guardrails  │        │
│  │ Integration  │  │   System     │        │
│  └──────────────┘  └──────────────┘        │
├─────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐        │
│  │  Prompt      │  │    CUDA      │        │
│  │ Compression  │  │ Acceleration │        │
│  └──────────────┘  └──────────────┘        │
└─────────────────────────────────────────────┘
```

**Current Capabilities**:
- ✅ Mistral 7B: 796ms avg, 100% EXCELLENT MCP tool calling
- ✅ Phi-3: 912ms avg, 100% EXCELLENT MCP tool calling
- ✅ DeepSeek: 100% success on multi-turn reasoning (4 turns, 5 tool calls)
- ✅ CUDA support: Phi-3 5x faster, Qwen 36x faster
- ✅ Automatic 50% prompt compression

**Next Steps**:
- 🔄 Additional native model support
- 🔄 Enhanced guardrails system
- 🔄 Streaming response support
- 🔄 Production deployment tools

**Use Cases**:
- Local AI-powered development tools
- Cost-effective inference for agents
- Multi-turn reasoning workflows
- Tool calling and MCP integration
- CUDA-accelerated inference

---

### 📐 **Compression Prompt** - Statistical Prompt Compression
**Location**: `./compression-prompt/`  
**Technology**: Rust (Pure Rust)  
**Status**: ✅ Operational (Production Ready)

**Purpose**: Fast, intelligent prompt compression for LLMs - Save 50% tokens while maintaining 91% quality.

**Key Features**:
- **Statistical Filtering**: 50% token reduction with 91% quality retention
- **Ultra Fast**: <1ms compression time (10.58 MB/s throughput)
- **LLM Validated**: 350+ test pairs across 6 flagship models (1.6M tokens)
- **Optical Context Compression**: Image output format (beta)
- **Pure Rust**: No external dependencies

**Architecture**:
```
┌─────────────────────────────────────────────┐
│       Compression Prompt Library             │
├─────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐        │
│  │ Statistical  │  │    Optical   │        │
│  │  Filtering   │  │  Rendering   │        │
│  └──────────────┘  └──────────────┘        │
├─────────────────────────────────────────────┤
│  IDF Scoring • Position Weight • POS       │
│  Entity Detection • Entropy Analysis        │
└─────────────────────────────────────────────┘
```

**Current Capabilities**:
- ✅ 50% compression with 91% quality (Claude Sonnet)
- ✅ 93% quality with Grok-4
- ✅ 100% keyword retention, 92% entity retention
- ✅ $2.50 savings per 1M tokens (Claude)
- ✅ 6 LLM validation (Grok-4, Claude, GPT-5, Gemini, Grok, Haiku)

**Next Steps**:
- 🔄 LangChain/LlamaIndex integration
- 🔄 Haystack document converters
- 🔄 Additional compression algorithms
- 🔄 v1.0.0 release

**Use Cases**:
- RAG systems (compress retrieved context)
- Q&A systems (reduce prompt size)
- Long document processing
- Cost optimization for LLM APIs
- Real-time applications

---

### 📋 **Rulebook** - AI Project Standardization CLI
**Location**: `./rulebook/`  
**Technology**: TypeScript/Node.js  
**Status**: ✅ Operational (v1.0.0 Production Ready)

**Purpose**: CLI tool to standardize AI-generated projects with templates, rules enforcement, and CI/CD generation for 11 languages.

**Key Features**:
- **Auto-Detection**: 11 programming languages
- **Template System**: 62 pre-built templates
- **Smart Merging**: Intelligent AGENTS.md merging
- **CI/CD Generation**: GitHub Actions workflows for test/lint/publish
- **Publishing Workflows**: 10 package registries (npm, crates.io, PyPI, etc.)
- **Health Checks**: Project quality validation
- **Auto-Fix**: Common issues automatically resolved

**Architecture**:
```
┌─────────────────────────────────────────────┐
│          Rulebook CLI                        │
├─────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐        │
│  │   Language   │  │   Template   │        │
│  │  Detection   │  │   System     │        │
│  └──────────────┘  └──────────────┘        │
├─────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐        │
│  │   Workflow   │  │    Health    │        │
│  │  Generation  │  │   Checks     │        │
│  └──────────────┘  └──────────────┘        │
└─────────────────────────────────────────────┘
```

**Current Capabilities**:
- ✅ 11 languages: Rust, TypeScript, Python, Go, Java, Elixir, C#, PHP, Swift, Kotlin, C/C++
- ✅ 23 AI tools/IDEs: Cursor, Windsurf, VS Code, JetBrains, etc.
- ✅ 5 MCP modules: Vectorizer, Synap, OpenSpec, Context7, GitHub
- ✅ 32 workflow templates: test, lint, publish for all languages

**Next Steps**:
- 🔄 Additional language support
- 🔄 Custom template enhancements
- 🔄 CI/CD monitoring integration
- 🔄 v2.0.0 release

**Use Cases**:
- Standardize AI-assisted development
- Auto-generate AGENTS.md files
- Create CI/CD workflows automatically
- Project health monitoring
- Documentation structure generation

---

### 💬 **Chat Hub** - AI Model Communication Hub
**Location**: `./chat-hub/`  
**Technology**: Node.js/TypeScript  
**Status**: ✅ Operational (Production Ready)

**Purpose**: Centralized communication and monitoring interface for AI model interactions across the HiveLLM ecosystem.

**Key Features**:
- **Real-time Monitoring**: Live AI model interaction tracking
- **36 AI Models**: 4 cursor-agent + 32 aider models
- **WebSocket Integration**: Real-time updates and notifications
- **Model Health Monitoring**: Availability and performance tracking
- **API Testing**: Built-in testing for all 36 models

**Architecture**:
```
┌─────────────────────────────────────────────┐
│          Chat Hub Server                     │
├─────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐        │
│  │  WebSocket   │  │     REST     │        │
│  │    Server    │  │     API      │        │
│  └──────────────┘  └──────────────┘        │
├─────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐        │
│  │    Model     │  │   Activity   │        │
│  │  Manager     │  │   Tracker    │        │
│  └──────────────┘  └──────────────┘        │
└─────────────────────────────────────────────┘
```

**Supported Models**:
- **Cursor-Agent (4)**: auto, gpt-5, sonnet-4, opus-4.1
- **Aider OpenAI (8)**: chatgpt-4o-latest, gpt-4o/mini, gpt-5-mini, etc.
- **Aider Anthropic (7)**: claude-4, sonnet-4, claude-3-7-sonnet, etc.
- **Aider Gemini (5)**: gemini-2.0-flash, gemini-2.5-pro/flash, etc.
- **Aider Grok (5)**: grok-4/3-latest, grok-3-fast/mini, etc.
- **Aider DeepSeek (4)**: deepseek-chat, deepseek-r1, deepseek-reasoner, etc.
- **Aider Groq (3)**: llama-3.1/3.3 variants

**Current Capabilities**:
- ✅ Real-time monitoring dashboard
- ✅ WebSocket integration
- ✅ Model health monitoring
- ✅ API testing utilities
- ✅ Activity tracking

**Next Steps**:
- 🔄 Enhanced model analytics
- 🔄 Conversation history tracking
- 🔄 Multi-agent orchestration interface
- 🔄 Production deployment tools

**Use Cases**:
- AI model health monitoring
- Real-time interaction tracking
- Model performance analytics
- Multi-agent conversation monitoring
- API connectivity testing

---

### 🖥️ **Studio** - Desktop Management Application
**Location**: `./studio/` (Planned)  
**Technology**: Electron/Tauri, TypeScript/Rust  
**Status**: 🔜 Planned Component

**Purpose**: Unified desktop application for installation, configuration, and management of all HiveLLM components.

**Key Features**:
- **Application Management**:
  - Install/uninstall Vectorizer, Synap, Voxa
  - Start/stop services
  - Monitor application status
  - Update management

- **Plugin System**:
  - Browse plugin marketplace
  - Install/remove plugins
  - Configure plugin settings
  - Plugin dependency management

- **Model Management**:
  - Download/install models
  - Model version control
  - Storage optimization
  - Model performance metrics

- **Interactive Chat**:
  - Direct chat with agent cluster
  - Multi-agent conversations
  - Context-aware interactions
  - Chat history management

- **Workspace Management**:
  - Create/manage workspaces
  - Workspace vectorization
  - Workspace sharing
  - Resource allocation per workspace

- **DevOps Tools**:
  - Generate K8s manifests
  - Create Terraform configurations
  - Infrastructure as code export
  - Deployment templates

- **Access Control**:
  - User authentication
  - Role-based permissions
  - Application access control
  - Audit logging

**Architecture**:
```
┌─────────────────────────────────────┐
│          Studio Desktop             │
├─────────────────────────────────────┤
│  UI Layer (Electron/Tauri)          │
├─────────────────────────────────────┤
│  Services Management                │
│  Plugin System                      │
│  Model Manager                      │
│  Chat Interface                     │
│  Workspace Manager                  │
│  DevOps Tools                       │
│  Access Control                     │
└─────────┬───────────────────────────┘
          │
    ┌─────┴─────┐
    │   UMICP   │
    └─────┬─────┘
          │
┌─────────┴──────────────────────┐
│  All HiveLLM Components        │
└────────────────────────────────┘
```

**Use Cases**:
- One-click HiveLLM installation
- Centralized component management
- Easy plugin installation
- Visual workspace management
- K8s/Terraform export for production

---

### 🧠 **Brain** - Standalone UMICP Orchestration Server
**Location**: `./brain/` (Planned)  
**Technology**: Rust (High Performance)  
**Status**: 🔜 Planned Component

**Purpose**: Standalone UMICP server for multi-peer agent orchestration with intelligent routing and load balancing, completely agnostic to agent implementations.

**Key Features**:
- **Multi-Peer Network**:
  - Support for unlimited agent peers
  - Dynamic peer discovery
  - Peer health monitoring
  - Automatic failover

- **Intelligent Orchestration**:
  - Smart request routing
  - Load balancing across agents
  - Priority queue management
  - Resource-aware scheduling

- **Agent Registry**:
  - Automatic agent registration
  - Capability advertisement
  - Agent metadata management
  - Service discovery

- **Network Management**:
  - Connection pooling
  - Circuit breakers
  - Rate limiting
  - Retry logic with backoff

- **Monitoring & Telemetry**:
  - Real-time network metrics
  - Agent performance tracking
  - Request/response logging
  - Bottleneck detection

- **Security**:
  - TLS/SSL encryption
  - Agent authentication
  - Authorization policies
  - Network segmentation

**Architecture**:
```
┌──────────┐     ┌──────────┐     ┌──────────┐
│ Agent A  │────►│  Brain   │◄────│ Agent B  │
└──────────┘     │ (UMICP   │     └──────────┘
┌──────────┐     │  Server) │     ┌──────────┐
│ Agent C  │────►│          │◄────│ Service  │
└──────────┘     └─────┬────┘     └──────────┘
                       │
              ┌────────┴────────┐
              │ Orchestration   │
              │ Registry        │
              │ Load Balancer   │
              │ Monitoring      │
              └─────────────────┘
```

**Plug-and-Play Model**:
- Any agent/service can connect to Brain
- Agents advertise their capabilities
- Other agents/services can discover and request services
- Brain handles routing, load balancing, and failover

**Use Cases**:
- Central orchestration hub for agent cluster
- Load distribution across agent instances
- Service mesh for microservices
- Agent capability discovery
- Network-wide monitoring

---

### 🔌 **IDE Extension** - VSCode Integration
**Location**: `./ide-extension/` (Planned)  
**Technology**: TypeScript, VSCode Extension API  
**Status**: 🔜 Planned Component

**Purpose**: VSCode extension for seamless integration with all HiveLLM tools and services.

**Key Features**:
- **Vectorizer Integration**:
  - Index workspace automatically
  - Semantic code search
  - Context-aware suggestions
  - Document Q&A

- **Agent Communication**:
  - Chat with agents directly in IDE
  - Request code reviews
  - Generate documentation
  - Refactoring assistance

- **Task Management**:
  - View and manage tasks from IDE
  - Create tasks from TODO comments
  - Assign tasks to agents
  - Track implementation progress

- **Governance Integration**:
  - View/create BIP proposals
  - Participate in voting
  - View meeting minutes
  - Governance dashboard

- **Workspace Features**:
  - Workspace vectorization status
  - Quick access to vectorized docs
  - Cross-project search
  - Knowledge graph visualization

- **DevOps Integration**:
  - Generate deployment configs
  - Preview K8s/Terraform
  - Deploy from IDE
  - Monitor deployments

- **Model Interaction**:
  - Select active model
  - Model performance metrics
  - Context window monitoring
  - Token usage tracking

**Architecture**:
```
┌─────────────────────────────────┐
│      VSCode Extension           │
├─────────────────────────────────┤
│  Sidebar Views                  │
│  Commands & Shortcuts           │
│  Status Bar Integration         │
│  Webview Panels                 │
└─────────┬───────────────────────┘
          │
    ┌─────┴──────┐
    │   Brain    │ (UMICP Network)
    │  (UMICP)   │
    └─────┬──────┘
          │
┌─────────┴────────────────────┐
│ Vectorizer, Task Queue,      │
│ Gateway, Agents, etc.        │
└──────────────────────────────┘
```

**Use Cases**:
- Code with AI assistance
- Semantic code navigation
- Automated documentation
- Task tracking in IDE
- Governance participation
- DevOps automation

---

### 🎓 **Tuning** - Model Training System
**Location**: `./tuning/` (Planned)  
**Technology**: Python, PyTorch, Transformers  
**Status**: 🔜 Planned Component

**Purpose**: System for training and fine-tuning models using LoRA with knowledge consolidated from Vectorizer, creating specialized expert models in transformer format.

**Key Features**:
- **LoRA Fine-Tuning**:
  - Low-Rank Adaptation training
  - Parameter-efficient fine-tuning
  - Merge LoRA weights
  - Multi-LoRA support

- **Vectorizer Integration**:
  - Use vectorized knowledge as training data
  - Semantic search for relevant examples
  - Context-aware data selection
  - Continuous learning from new documents

- **Model Management**:
  - Support for multiple model architectures
  - Model versioning
  - A/B testing framework
  - Performance benchmarking

- **Training Pipeline**:
  - Data preprocessing
  - Training job scheduling
  - Distributed training support
  - Checkpoint management

- **Specialized Models**:
  - Domain-specific experts
  - Task-specific fine-tuning
  - Multi-task learning
  - Transfer learning

- **Evaluation**:
  - Automated evaluation metrics
  - Human evaluation framework
  - Regression testing
  - Performance tracking

**Architecture**:
```
┌─────────────────────────────────┐
│      Tuning System              │
├─────────────────────────────────┤
│  LoRA Trainer                   │
│  Data Pipeline                  │
│  Model Manager                  │
│  Evaluation Suite               │
└─────────┬───────────────────────┘
          │
    ┌─────▼──────┐
    │ Vectorizer │ (Knowledge Base)
    └─────┬──────┘
          │
    ┌─────▼──────┐
    │  HiveGPU   │ (Training Acceleration)
    └────────────┘
```

**Training Workflow**:
1. Extract knowledge from Vectorizer
2. Prepare training dataset
3. Fine-tune base model with LoRA
4. Evaluate performance
5. Deploy specialized model
6. Monitor and iterate

**Use Cases**:
- Create domain-specific expert models
- Fine-tune for specific tasks
- Personalize models with company knowledge
- Continuous model improvement
- Multi-tenant specialized models

---

### 🏢 **2B** - Enterprise Customer Management System
**Location**: `./2b/` (Planned)  
**Technology**: TypeScript, Node.js, React  
**Status**: 🔜 Planned Component

**Purpose**: Comprehensive B2B customer management system for HiveLLM Enterprise, handling all aspects of customer relationship and business operations.

**Key Features**:
- **Call Management**:
  - Inbound/outbound call tracking
  - Call recording and transcription
  - Call analytics and metrics
  - Integration with VoIP systems

- **Bug Tracking**:
  - Issue creation and tracking
  - Priority and severity management
  - Bug lifecycle management
  - Integration with development tools

- **Payment Processing**:
  - Invoice generation
  - Payment gateway integration
  - Subscription management
  - Payment history and reports

- **Billing & Invoicing**:
  - Automated invoice generation
  - Brazilian fiscal note (NF-e) emission
  - Tax calculation
  - Payment reminders

- **Support Scheduling**:
  - Appointment booking
  - Support calendar management
  - Automated reminders
  - Video call integration

- **FAQ System**:
  - Knowledge base management
  - Self-service portal
  - AI-powered search
  - Automatic FAQ generation from tickets

- **CRM Features**:
  - Customer profiles and history
  - Contact management
  - Opportunity tracking
  - Sales pipeline
  - Customer segmentation
  - Activity timeline

- **Analytics & Reporting**:
  - Customer satisfaction metrics
  - Support performance KPIs
  - Revenue analytics
  - Custom reports

- **Multi-tenant Support**:
  - Isolated customer environments
  - Custom branding per tenant
  - Tenant-specific configurations
  - Resource allocation management

**Architecture**:
```
┌─────────────────────────────────────┐
│         2B System                   │
├─────────────────────────────────────┤
│  Call Management                    │
│  Bug Tracking                       │
│  Payment & Billing                  │
│  Support Scheduling                 │
│  FAQ & Knowledge Base               │
│  CRM & Sales Pipeline               │
│  Analytics & Reporting              │
└─────────┬───────────────────────────┘
          │
    ┌─────┴──────┐
    │ Vectorizer │ (Customer Knowledge)
    └─────┬──────┘
          │
    ┌─────┴──────┐
    │   Voxa     │ (Voice Support)
    └────────────┘
```

**Integration Points**:
- **Vectorizer**: Store customer knowledge, FAQ, documentation
- **Voxa**: Voice-based customer support
- **Task Queue**: Automated support workflows
- **Agent Framework**: AI-powered support agents
- **Brain**: Orchestrate support operations

**Use Cases**:
- Manage enterprise customer base
- Track support tickets and bugs
- Process payments and issue invoices
- Schedule support appointments
- Maintain customer knowledge base
- Analyze customer satisfaction
- Automate support workflows

---

## 🔗 Component Integration Matrix

| Component | Integrates With | Protocol | Purpose |
|-----------|----------------|----------|---------|
| **gov** | All components | UMICP, REST | Governance & coordination |
| **vectorizer** | All agents | MCP, REST, UMICP | Persistent memory |
| **UMICP** | All components | Native | Communication backbone |
| **Voxa** | Vectorizer, Task Queue, Agents | UMICP, MCP | Human interface |
| **Task Queue** | Agents, Framework | UMICP, REST | Task orchestration |
| **Gateway** | All agents | MCP, REST | Tool access & permissions |
| **Agent Framework** | All components | MCP, REST, UMICP | Agent creation |
| **Synap** | All components | MCP/UMICP/REST | In-memory data infrastructure |
| **Transmutation** | Vectorizer | Direct | Document conversion |
| **Nexus** | Vectorizer | Hybrid | Graph + vector search |
| **Reasoning** | Vectorizer | MCP | LLM inference engine |
| **Compression Prompt** | All LLMs | Library | Prompt compression |
| **Rulebook** | All projects | CLI | Project standardization |
| **Chat Hub** | 36 AI Models | WebSocket/REST | Model communication |
| **HiveGPU** | Vectorizer, Tuning | Native | GPU acceleration |
| **Studio** | All components | UMICP, REST | Management UI |
| **Brain** | All agents & services | UMICP | Orchestration hub |
| **IDE Extension** | Vectorizer, Task Queue, Brain | UMICP, MCP | Development integration |
| **Tuning** | Vectorizer, HiveGPU | REST, Native | Model training |
| **2B** | Vectorizer, Voxa, Agents | UMICP, REST | Enterprise customer management |

---

## 🎯 System Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                        HiveLLM Ecosystem                         │
└─────────────────────────────────────────────────────────────────┘
                                │
         ┌──────────────────────┼──────────────────────┐
         │                      │                      │
    ┌────▼────┐           ┌─────▼─────┐         ┌─────▼─────┐
    │ Studio  │           │    gov    │         │    2B     │
    │ (Mgmt)  │           │ (Control) │         │(Customer) │
    └────┬────┘           └─────┬─────┘         └─────┬─────┘
         │                      │                      │
         └──────────────────────┼──────────────────────┘
                                │
            ┌───────────────────┼───────────────────┐
            │                   │                   │
      ┌─────▼────┐        ┌─────▼────┐       ┌─────▼────────┐
      │  Voxa    │        │ Gateway  │       │IDE Extension │
      │ (Human)  │        │ (Tools)  │       │    (Dev)     │
      └─────┬────┘        └─────┬────┘       └─────┬────────┘
            │                   │                   │
            └───────────────────┼───────────────────┘
                                │
                      ┌─────────▼──────────┐
                      │       Brain        │
                      │  (Orchestration)   │
                      └─────────┬──────────┘
                                │
                      ┌─────────▼──────────┐
                      │      UMICP         │
                      │  (Communication)   │
                      └─────────┬──────────┘
                                │
       ┌────────────────────────┼────────────────────────┐
       │                        │                        │
  ┌────▼────┐            ┌──────▼──────┐          ┌─────▼──────┐
  │Vectorizer│           │ Task Queue  │          │   Synap    │
  │(Memory) │            │ (Workflow)  │          │(Streaming) │
  └────┬────┘            └──────┬──────┘          └─────┬──────┘
       │                        │                        │
       └────────────────────────┼────────────────────────┘
                                │
                      ┌─────────▼──────────┐
                      │  Agent Framework   │
                      │   (Specialized     │
                      │     Agents)        │
                      └─────────┬──────────┘
                                │
                 ┌──────────────┼──────────────┐
                 │              │              │
            ┌────▼─────┐   ┌────▼────┐   ┌────▼────┐
            │ HiveGPU  │   │ Tuning  │   │ Models  │
            │  (GPU)   │   │(Training│   │  (LLMs) │
            └──────────┘   └─────────┘   └─────────┘
```

### Architecture Layers

**Layer 1 - Management & Business**:
- **Studio**: Central management application
- **gov**: Governance and decision-making
- **2B**: Enterprise customer management

**Layer 2 - Human & Developer Interface**:
- **Voxa**: Voice interaction
- **Gateway**: Tool access management
- **IDE Extension**: Development integration

**Layer 3 - Orchestration**:
- **Brain**: Intelligent agent orchestration
- **UMICP**: Universal communication protocol

**Layer 4 - Core Services**:
- **Vectorizer**: Persistent memory
- **Task Queue**: Workflow orchestration
- **Synap**: Event streaming

**Layer 5 - Agent Platform**:
- **Agent Framework**: Agent development and deployment

**Layer 6 - AI Infrastructure**:
- **HiveGPU**: GPU acceleration
- **Tuning**: Model training
- **Models**: LLM instances

---

## 📈 Development Status Summary

| Component | Status | Completion | Next Priority |
|-----------|--------|-----------|---------------|
| **gov** | 🔄 Active | 70% | Multi-agent dashboard |
| **vectorizer** | ✅ Operational | 85% | Plugin system, GPU integration |
| **UMICP** | ✅ Operational | 95% | Ecosystem integration |
| **Voxa** | 🔄 Development | 40% | STT/TTS integration |
| **Task Queue** | ✅ Operational | 75% | Advanced orchestration |
| **Gateway** | 🔄 Development | 60% | Permission system |
| **Agent Framework** | 🔄 Active | 65% | Multi-language support |
| **Synap** | ✅ Operational | 95% | Clustering, monitoring |
| **Transmutation** | ✅ Operational | 90% | C++ FFI, v1.0 release |
| **Nexus** | 🔄 Development | 30% | MVP storage, Cypher support |
| **Reasoning** | ✅ Operational | 85% | Additional model support |
| **Compression Prompt** | ✅ Operational | 95% | Framework integrations |
| **Rulebook** | ✅ Operational | 90% | v2.0 enhancements |
| **Chat Hub** | ✅ Operational | 80% | Enhanced analytics |
| **HiveGPU** | 🔜 Planned | 0% | Initial implementation |
| **Studio** | 🔜 Planned | 0% | UI/UX design, architecture |
| **Brain** | 🔜 Planned | 0% | Orchestration engine design |
| **IDE Extension** | 🔜 Planned | 0% | VSCode extension skeleton |
| **Tuning** | 🔜 Planned | 0% | LoRA training pipeline |
| **2B** | 🔜 Planned | 0% | CRM architecture design |

**Legend**:
- ✅ Operational: Core features working
- 🔄 Active Development: Being actively built
- 🔜 Planned: Design phase

**Total Components**: 20 (12 operational, 3 in development, 5 planned)

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** 18+ (for TypeScript components)
- **Python** 3.10+ (for Voxa and utilities)
- **Rust** 1.75+ (for Vectorizer, Task Queue, Synap)
- **C++17** (for UMICP, HiveGPU)

### Quick Start
```bash
# Clone the ecosystem repository
git clone --recurse-submodules https://github.com/hivellm/hivellm.git
cd hivellm

# Each component can be started independently
cd vectorizer && cargo run --release
cd task-queue && cargo run
cd voxa && python main.py
```

### Development Workflow
Each component operates independently but integrates through:
- **UMICP** for inter-component communication
- **MCP** for agent-tool integration
- **REST** for web interfaces and external access

---

**Maintained by**: HiveLLM Core Team  
**Last Updated**: October 2025  
**Version**: Ecosystem v2.0

---

## 📖 Related Documentation
- [Ecosystem Creation Summary](./ECOSYSTEM_CREATION_SUMMARY.md) - Evolution and philosophy
- [Ecosystem Status](./ECOSYSTEM_STATUS.md) - Current development status
- [Ecosystem DAG](./ECOSYSTEM_DAG.md) - Dependency graph and architecture layers
- [Main README](../../README.md) - Project overview