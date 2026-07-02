<div align="center">

# SuperInference

### Sovereign AI Agents for Software Engineering

[![Website](https://img.shields.io/badge/Website-superinference.org-000?style=flat-square)](https://superinference.org)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue?style=flat-square)](https://github.com/superinference/ami/blob/main/LICENSE)
[![VS Code](https://img.shields.io/badge/VS_Code-Extension-007ACC?style=flat-square&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=superinference.ami-vscode)

</div>

---

**SuperInference** is a research framework for iterative LLM reasoning with information-theoretic stopping criteria. **AMI** (Agentic Multi-step Inference) is the coding agent built on it — model-agnostic, sovereign, and free.

| Benchmark | Rank | Score | Model |
|-----------|------|-------|-------|
| **SWE-bench-Live Lite** | **#1** | **63.0%** resolved | AMI + Claude-4.6-Opus |
| **DABStep Hard Tasks** | **#3** | **41.3%** accuracy | SuperInference + Gemini 2.5 Pro |

## Install

```bash
curl -fsSL https://www.superinference.org/install.sh | bash
```

## Why AMI

- **Any model** — OpenAI, Anthropic, Google, Groq, Mistral, Ollama, vLLM, or any OpenAI-compatible API
- **Zero cost** — FRITO routes through free-tier providers with automatic rotation on rate limits
- **Sovereign** — runs on your infrastructure, air-gapped deployable, no telemetry, no cloud dependencies
- **45+ tools** — file ops, code search, shell execution, web access, MCP, workflow orchestration
- **PRE loop** — Plan, Retrieve, Execute with critic-gated memory and information-theoretic stopping

## Sovereign AI

AMI is designed for environments that require full control over AI infrastructure — aligned with EU sovereign cloud requirements. The agent runs on-premise, connects to self-hosted models, and operates fully disconnected. The SuperInference framework is open source. AMI is distributed under the Apache 2.0 license.

## Research

| Paper | Year |
|-------|------|
| **AMI: Agentic Multi-Step Inference for Autonomous Software Engineering** | 2026 |
| **SuperInference: Supervised Inference for Partially Observable Environments** | 2026 |

## Links

| | |
|---|---|
| **Website** | [superinference.org](https://superinference.org) |
| **Docs** | [superinference.org/docs](https://superinference.org/docs) |
| **Leaderboards** | [superinference.org/leaderboards](https://superinference.org/leaderboards) |
| **Research** | [superinference.org/research](https://superinference.org/research) |
