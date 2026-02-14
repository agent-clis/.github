# agent-clis

**CLI tools designed for agents.** [agent-clis.sh](https://agent-clis.sh)

Software has always been built for human users. That era is ending. Agents are becoming the primary executors of software workflows — browsing, building, deploying, debugging — and the tools they rely on were never designed for how they work. They can't verify safety before execution. They can't report friction when something breaks. They can't compose tools through validated contracts.

agent-clis is an open-source ecosystem of CLI tools built agent-first: structured I/O, zero GUI dependencies, programmatic error reporting, and machine-readable output by default. Humans benefit from these tools too, but agents are the design target.

## The Stack

### Trust — Can the agent safely do what it's about to do?

| Tool | Description | Status |
|------|-------------|--------|
| [skill-issue](https://github.com/agent-clis/skill-issue) | Static security analyzer for AI skill directories. 50+ rules for prompt injection, credential leaks, obfuscated content, and social engineering patterns. | ![Released](https://img.shields.io/badge/status-released-brightgreen) |
| [cage.sh](https://github.com/agent-clis/cage) | Sandboxed execution for untrusted scripts. Restricted filesystem, network, and resource limits. Apple containerization on macOS, Firecracker on Linux. Built in Rust. | ![Planned](https://img.shields.io/badge/status-planned-lightgrey) |
| [contract.sh](https://github.com/agent-clis/contract) | Input/output contract validation for CLI tools. Type checking for shell pipelines. Verifies the seams between chained tools in agent workflows. | ![Planned](https://img.shields.io/badge/status-planned-lightgrey) |

### Orchestration — How does the agent compose and execute work?

| Tool | Description | Status |
|------|-------------|--------|
| [atomic-dag.sh](https://github.com/agent-clis/atomic-dag) | Multilingual DAG runner. Define tasks as Python or TypeScript scripts with TOML dependencies. Topological sort, parallel execution, mid-graph resumption. Built in Rust. | ![Planned](https://img.shields.io/badge/status-planned-lightgrey) |
| [mcp2cli](https://github.com/agent-clis/mcp2cli) | Convert any MCP server into a CLI. Introspects tool catalogs, generates subcommands from schemas. Makes MCP servers testable, composable, and debuggable without an agent framework. | ![Planned](https://img.shields.io/badge/status-planned-lightgrey) |
| [mcp-progressive-disclosure](https://github.com/agent-clis/mcp-progressive-disclosure) | Context-aware MCP proxy. Surfaces tool names by default, expands full schemas on demand. Implements progressive disclosure for AI tool interfaces to prevent context rot. | ![Planned](https://img.shields.io/badge/status-planned-lightgrey) |
| [mock-api.sh](https://github.com/agent-clis/mock-api) | Instant fake API from an OpenAPI spec. One command, zero config. Agents building frontends can test without waiting for a real backend. | ![Planned](https://img.shields.io/badge/status-planned-lightgrey) |

### Productivity — What does the agent actually produce?

| Tool | Description | Status |
|------|-------------|--------|
| [gripe.sh](https://github.com/agent-clis/gripe) | Structured feedback as GitHub issues from the CLI. YAML schema → interactive or automated issue creation. Agents report friction they encounter during execution without human intervention. | ![In Development](https://img.shields.io/badge/status-in%20development-yellow) |
| [diagrams.sh](https://github.com/agent-clis/diagrams) | Architecture diagrams from YAML. CLI renders to SVG, PNG, and native PPTX. No browser, no drag-and-drop. | ![In Development](https://img.shields.io/badge/status-in%20development-yellow) |
| [decks.sh](https://github.com/agent-clis/decks) | Slide decks from atomic JS snippets. Each slide is an independent file, enabling parallel generation by multiple agents with unified theming. Single binary via Bun. | ![Planned](https://img.shields.io/badge/status-planned-lightgrey) |
| [next-on-rails](https://github.com/agent-clis/next-on-rails) | Bootstrap a fully wired Next.js project across Vercel, Clerk, Neon, and Resend. DNS, callback URLs, env vars, and domain verification from a single command. | ![Planned](https://img.shields.io/badge/status-planned-lightgrey) |

## Design Principles

**Structured I/O.** Every tool accepts and emits JSON. Human-readable output is the secondary format, not the default.

**Zero runtime dependencies.** Single binaries where possible. No Python version conflicts, no node_modules, no Docker required.

**Composable by default.** Tools are designed to chain. The output of one is the input of another. `contract.sh` validates the seams.

**Feedback loops built in.** When a tool fails, `gripe.sh` gives agents a voice. Maintainers opt in with `automated: allow`. Consent-based, not spam.

## Contributing

Each tool lives in its own repository under this org. Issues, PRs, and feedback welcome — including via `gripe submit`.

## License

Each tool is individually licensed. See the respective repository for details.
