# 🚀 HiveLLM Quick Reference

**Quick access guide to the HiveLLM ecosystem**

---

## 📋 Component Status at a Glance

| Component | Purpose | Tech | Status | Start Command |
|-----------|---------|------|--------|---------------|
| **gov** | Governance | TypeScript | 🔄 70% | `cd governance && npm start` |
| **vectorizer** | Memory | Rust | ✅ 85% | `cd vectorizer && cargo run --release` |
| **UMICP** | Communication | C++ | ✅ 95% | `cd umicp/build && ./examples/basic_example` |
| **Synap** | In-Memory Data | Rust | ✅ 95% | `cd synap && cargo run --release` |
| **Transmutation** | Doc Conversion | Rust | ✅ 90% | `cd transmutation && cargo run --release` |
| **Reasoning** | LLM Inference | Rust | ✅ 85% | `cd ide/reasoning && cargo run` |
| **Compression Prompt** | Prompt Compress | Rust | ✅ 95% | `cd compression-prompt/rust && cargo run` |
| **Rulebook** | Standardization | TypeScript | ✅ 90% | `cd rulebook && npm start` |
| **Chat Hub** | Model Monitor | Node.js | ✅ 80% | `cd chat-hub && node server.js` |
| **Task Queue** | Orchestration | Rust | ✅ 75% | `cd task-queue && cargo run` |
| **Voxa** | Voice UI | Python | 🔄 40% | `cd voxa && python main.py` |
| **Gateway** | MCP Tools | TypeScript | 🔄 60% | `cd gateway && npm start` |
| **Agent Framework** | Agent Dev | TypeScript | 🔄 65% | `cd agent-framework && npm start` |
| **Nexus** | Graph Database | Rust | 🔄 30% | `cd nexus && cargo run` |
| **HiveGPU** | GPU Compute | C++/Rust | 🔜 0% | *Planned* |
| **Studio** | Management UI | Electron/Tauri | 🔜 0% | *Planned* |
| **Brain** | Orchestration | Rust | 🔜 0% | *Planned* |
| **IDE Extension** | VSCode Plugin | TypeScript | 🔜 0% | *Planned* |
| **Tuning** | Model Training | Python | 🔜 0% | *Planned* |
| **2B** | Enterprise CRM | TypeScript | 🔜 0% | *Planned* |

**Total**: 20 components (12 operational, 3 in development, 5 planned)

---

## 🔌 Integration Protocols

### MCP (Model Context Protocol)
**Used by**: vectorizer, Gateway, Agent Framework

```bash
# Vectorizer MCP
cd vectorizer
cargo run --release -- --mcp

# Configure in MCP client
{
  "mcpServers": {
    "vectorizer": {
      "command": "cargo",
      "args": ["run", "--release", "--", "--mcp"]
    }
  }
}
```

### REST API
**Used by**: vectorizer, gov, Task Queue

```bash
# Vectorizer REST
curl http://localhost:15001/search -d '{"query": "example", "limit": 5}'

# Task Queue REST
curl http://localhost:8080/tasks

# Governance REST
curl http://localhost:3000/api/proposals
```

### UMICP Protocol
**Used by**: All components (future)

```typescript
import { UMICPClient } from '@hivellm/umicp';

const client = new UMICPClient('ws://localhost:7000');
await client.connect();
await client.send('agent.task', { task: 'example' });
```

---

## 🛠️ Common Commands

### Build Everything
```bash
# Rust components
cd vectorizer && cargo build --release
cd task-queue && cargo build --release

# TypeScript components
cd governance && npm install && npm run build
cd gateway && npm install && npm run build
cd agent-framework && npm install && npm run build

# C++ components
cd umicp && mkdir -p build && cd build && cmake ../cpp && make

# Python components
cd voxa && pip install -r requirements.txt
```

### Run Tests
```bash
# Rust tests
cd vectorizer && cargo test
cd task-queue && cargo test

# TypeScript tests
cd governance && npm test
cd gateway && npm test
cd agent-framework && npm test

# C++ tests
cd umicp/build && ctest

# Python tests
cd voxa && pytest
```

### Development Mode
```bash
# Rust with auto-reload (cargo-watch)
cd vectorizer && cargo watch -x run

# TypeScript with auto-reload
cd governance && npm run dev
cd gateway && npm run dev
cd agent-framework && npm run dev

# Python with auto-reload
cd voxa && python -m flask run --reload
```

---

## 📂 Directory Structure

```
hivellm/
├── agent-framework/          # Agent development framework
│   ├── typescript/           # TypeScript implementation
│   └── docs/                 # Framework documentation
│
├── gateway/                  # MCP tools manager
│   ├── src/                  # Source code
│   └── docs/                 # API documentation
│
├── gov/                      # Governance repository
│   ├── bips/                 # BIP proposals
│   ├── proposals/            # Active proposals
│   └── minutes/              # Meeting records
│
├── governance/               # Governance dashboard
│   ├── src/                  # Dashboard source
│   └── public/               # Frontend assets
│
├── task-queue/               # Task orchestration
│   ├── src/                  # Rust source
│   ├── dashboard/            # Web dashboard
│   └── cli/                  # CLI tools
│
├── umicp/                    # Communication protocol
│   ├── cpp/                  # C++ core
│   └── bindings/             # Language bindings
│       ├── typescript/
│       ├── python/
│       ├── rust/
│       └── go/
│
├── vectorizer/               # Vector database
│   ├── src/                  # Rust source
│   ├── client-sdks/          # Client libraries
│   └── docs/                 # Documentation
│
├── voxa/                     # Voice assistant
│   ├── models/               # STT/TTS models
│   └── docs/                 # Documentation
│
└── docs/                     # Ecosystem documentation
    ├── ecosystem/            # This guide
    └── governance/           # Governance docs
```

---

## 🔗 Important URLs (Default Ports)

| Service | Port | URL | Purpose |
|---------|------|-----|---------|
| Governance Dashboard | 3000 | http://localhost:3000 | Governance UI |
| Vectorizer MCP | 15001 | - | MCP Server |
| Vectorizer REST | 15001 | http://localhost:15001 | REST API |
| Task Queue | 8080 | http://localhost:8080 | Task API |
| Task Queue Dashboard | 3001 | http://localhost:3001 | Task UI |
| UMICP Server | 7000 | ws://localhost:7000 | WebSocket |
| Gateway | 3002 | http://localhost:3002 | MCP Gateway |
| Agent Framework | 3003 | http://localhost:3003 | Agent API |

*Note: Ports are configurable in each component's config file*

---

## 🎯 Quick Problem Solving

### Vectorizer Not Starting
```bash
# Check if port is in use
lsof -i :15001  # Unix
netstat -ano | findstr :15001  # Windows

# Clear data and restart
cd vectorizer
rm -rf data/
cargo run --release
```

### UMICP Build Issues
```bash
# Install dependencies (Ubuntu)
sudo apt-get install cmake g++ libssl-dev

# Clean build
cd umicp
rm -rf build
mkdir build && cd build
cmake ../cpp && make
```

### Task Queue Database Locked
```bash
cd task-queue
rm task-queue-data/*.db-wal
rm task-queue-data/*.db-shm
cargo run
```

### Governance Dashboard Not Loading
```bash
cd governance
rm -rf node_modules package-lock.json
npm install
npm run build
npm start
```

---

## 📊 Health Check Commands

### Check All Services
```bash
# Vectorizer
curl -s http://localhost:15001/health || echo "Vectorizer DOWN"

# Task Queue
curl -s http://localhost:8080/health || echo "Task Queue DOWN"

# Governance
curl -s http://localhost:3000/health || echo "Governance DOWN"

# UMICP (if running)
# Check process: ps aux | grep umicp
```

### Check Logs
```bash
# Vectorizer logs
tail -f vectorizer/logs/vectorizer.log

# Task Queue logs
tail -f task-queue/logs/queue.log

# Governance logs
tail -f governance/logs/combined.log
```

---

## 🧪 Testing Workflows

### Test Vectorizer Memory
```bash
cd vectorizer

# Index a document
curl -X POST http://localhost:15001/index \
  -H "Content-Type: application/json" \
  -d '{"content": "Test document", "metadata": {"source": "test"}}'

# Search
curl -X POST http://localhost:15001/search \
  -H "Content-Type: application/json" \
  -d '{"query": "test", "limit": 5}'
```

### Test Task Queue
```bash
cd task-queue

# Create a task
curl -X POST http://localhost:8080/tasks \
  -H "Content-Type: application/json" \
  -d '{"title": "Test task", "priority": "high"}'

# List tasks
curl http://localhost:8080/tasks
```

### Test UMICP Communication
```bash
cd umicp/build

# Run test client
./examples/client_example ws://localhost:7000
```

---

## 📚 Documentation Links

### Core Docs
- [Ecosystem Map](./ECOSYSTEM_MAP.md) - Component details
- [Ecosystem Status](./ECOSYSTEM_STATUS.md) - Current status
- [Creation Summary](./ECOSYSTEM_CREATION_SUMMARY.md) - Project evolution
- [Ecosystem DAG](./ECOSYSTEM_DAG.md) - Dependency graph

### Commercial Docs (Portuguese)
- [Pitch Comercial](./PITCH_COMERCIAL.md) - Complete commercial pitch (detailed)
- [Elevator Pitch](./ELEVATOR_PITCH.md) - 1-page quick pitch
- [Sumário Executivo](./SUMARIO_EXECUTIVO.md) - Executive summary (handout)
- [Apresentação Comercial](./APRESENTACAO_COMERCIAL.md) - Slide deck (23 slides)
- [FAQ Comercial](./FAQ_COMERCIAL.md) - Common objections and answers

### Component READMEs
- [gov/README.md](../../gov/README.md)
- [governance/README.md](../../governance/README.md)
- [vectorizer/README.md](../../vectorizer/README.md)
- [umicp/README.md](../../umicp/README.md)
- [voxa/README.md](../../voxa/README.md)
- [task-queue/README.md](../../task-queue/README.md)
- [gateway/README.md](../../gateway/README.md)
- [agent-framework/README.md](../../agent-framework/README.md)

### API Documentation
- [Vectorizer API](../../vectorizer/docs/API.md)
- [Task Queue API](../../task-queue/docs/API.md)
- [UMICP Protocol](../../umicp/docs/PROTOCOL.md)
- [Gateway API](../../gateway/docs/API_SPEC.md)

---

## 🚨 Emergency Commands

### Kill All Services
```bash
# Unix/Linux
pkill -f "vectorizer"
pkill -f "task-queue"
pkill -f "governance"
pkill -f "umicp"

# Windows
taskkill /F /IM vectorizer.exe
taskkill /F /IM task-queue.exe
taskkill /F /IM node.exe  # Governance dashboard
```

### Reset Everything
```bash
# WARNING: This will delete all data!

# Stop services first
pkill -f "vectorizer|task-queue|governance"

# Clear data
rm -rf vectorizer/data/
rm -rf task-queue/task-queue-data/
rm -rf governance/governance.db*

# Rebuild
cd vectorizer && cargo build --release
cd task-queue && cargo build --release
cd governance && npm install && npm run build
```

### Backup Current State
```bash
# Create backup directory
mkdir -p backups/$(date +%Y%m%d)

# Backup data
cp -r vectorizer/data/ backups/$(date +%Y%m%d)/vectorizer-data
cp -r task-queue/task-queue-data/ backups/$(date +%Y%m%d)/task-queue-data
cp governance/governance.db* backups/$(date +%Y%m%d)/
```

---

## 🔧 Environment Variables

### Vectorizer
```bash
VECTORIZER_PORT=15001
VECTORIZER_DATA_DIR=./data
VECTORIZER_LOG_LEVEL=info
```

### Task Queue
```bash
TASK_QUEUE_PORT=8080
TASK_QUEUE_DB=./task-queue-data
TASK_QUEUE_LOG_LEVEL=info
```

### Governance
```bash
GOV_PORT=3000
GOV_DB=./governance.db
GOV_LOG_LEVEL=debug
```

### UMICP
```bash
UMICP_PORT=7000
UMICP_LOG_LEVEL=info
```

---

## 🎓 Learning Path

### For New Contributors
1. Read [README.md](../../README.md)
2. Review [Ecosystem Map](./ECOSYSTEM_MAP.md)
3. Choose a component to explore
4. Read component's README
5. Run basic examples
6. Try making small changes

### For Agent Developers
1. Understand [Agent Framework](../../agent-framework/README.md)
2. Learn [UMICP Protocol](../../umicp/README.md)
3. Explore [Vectorizer integration](../../vectorizer/README.md)
4. Review [Task Queue workflows](../../task-queue/README.md)
5. Build your first agent

### For System Integrators
1. Review [Integration Protocols](#integration-protocols)
2. Study [UMICP bindings](../../umicp/bindings/)
3. Test [MCP integrations](#mcp-model-context-protocol)
4. Implement REST clients
5. Deploy full stack

---

## 📞 Get Help

### Documentation
- Check component README
- Review API documentation
- Read ecosystem guides

### Debugging
- Check logs in component's logs/ directory
- Run health checks
- Test with curl/postman

### Community
- GitHub Issues: Report bugs
- GitHub Discussions: Ask questions
- Contributing Guide: [CONTRIBUTING.md](../../CONTRIBUTING.md)

---

**Quick Reference Version**: 1.0  
**Last Updated**: October 2025  
**Maintained by**: HiveLLM Core Team

