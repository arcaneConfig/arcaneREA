# REA (Reverse Engineer Anything) 🔍🤖

**REA** is an open-source framework and Model Context Protocol (MCP) server that connects your AI coding agents directly to specialized tools for reverse engineering. It bridges the gap between high-level app behavior and low-level artifacts—allowing agents to inspect website frontends, Electron boundaries, .NET assemblies, and even compiled native binaries without requiring access to original source code.

---

## ⚙️ How REA Works

REA structures the reverse engineering process into a repeatable, systematic **Five-Stage Framework** that guides your AI agent through complex investigation:

1. **Pick a Feature:** Instead of instructing an agent to "clone an entire app," you isolate one specific piece of functionality (e.g., a draggable camera bubble, a sound-pan calculation, or an IPC clipboard bridge).
2. **Route by Build:** The agent inspects what technology stack the target is built with (e.g., static JavaScript, .NET, Electron, or native binaries) to choose the appropriate analysis pathway.
3. **Summary First:** Findings and code structures are summarized and cached locally so the agent doesn't waste context tokens running massive redundant analyses on subsequent loops.
4. **Seen, Inferred, Unknown Tagging:** REA strictly separates what facts are directly observed (seen), what is logically deduced (inferred), and what remains missing (unknown). This prevents agents from hallucinating functionality or debugging based on false assumptions.
5. **Rebuild & Test:** Findings are immediately translated into clean, independent code implementations and validated against targeted test behaviors, focusing strictly on functional replication rather than copying exact intellectual property.

Your AI agent interacts with REA via **MCP (Model Context Protocol)**, issuing calls to inspect target structures, trace execution logic, and return verifiable evidence back to its working context.

---

## 🚀 Getting Started & Installation

### Prerequisites
* **Node.js** and **npm** installed on your system.
* A compatible AI agent client that supports local MCP servers (such as Claude Code or other MCP-compatible coding interfaces).
* *(Optional for native binaries)* A native analysis engine such as **Hopper** (which REA can help prompt/install), **Ghidra**, or **IDA Pro**.

### 1. Set Up Your Agent
Run the interactive setup command from your terminal:
```bash
npx rea-agents setup
```
* This command guides you through choosing your agent targets, reviewing configuration changes, backing up existing settings, and registering REA's MCP server alongside the required workflow instructions.
* *Note:* Restart your agent client after running setup to ensure the new MCP tools and skill files are loaded.

### 2. Install Globally (Optional for CLI usage)
If you want to run REA utility commands directly from your terminal, install it globally via npm or bun:
```bash
npm install --global rea-agents rea
# Or using bun:
# bun add --global rea-agents rea
```

---

## 💻 How to Use This Project

### Using REA via Your AI Agent (MCP Integration)
Once set up, you can prompt your AI agent naturally to investigate features inside your target application path or build. For example:
> *"Inspect the module boundaries and imports in `D:/apps/example`, trace how the clipboard event is handled across the Electron main-to-renderer boundary, and draft an independent implementation for our project."*

The agent will query REA via MCP, review the returned evidence, ask clarifying questions, and write a tested, clean-room implementation.

### Using the REA CLI
For direct command-line operations, snapshots, or scripting workflows:
```bash
rea --help
```
Depending on your target type, provide the file path or package directory to begin extraction. For native binaries, ensure your chosen provider (like Hopper) is accessible in your session environment.

---

## 🔄 Keeping REA Up to Date
Because REA evolves rapidly with frequent updates and bug fixes, you can update your global installation at any time:
```bash
rea update
```
If you are running via `npx`, pull the latest version and refresh your agent configuration by executing:
```bash
npx rea-agents@latest setup
```

---

## ⚠️ Best Practices & Legal Notice
* **Focus on Functionality, Not IP:** Use REA to understand *mechanics, algorithms, and interaction models*, not to lift proprietary source code, graphic assets, or text verbatim. 
* **Verify Inferences:** Always instruct your agent to double-check inferred code blocks with explicit unit tests during the rebuild phase.