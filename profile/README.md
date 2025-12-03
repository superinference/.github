<div align="center">

# 🧠 SuperInference

### Feedback-Augmented LLM Agents for Complex Programming and Multi-Step Reasoning

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![arXiv](https://img.shields.io/badge/arXiv-2506.XXXXX-b31b1b.svg)](https://arxiv.org/)
[![VS Code Extension](https://img.shields.io/badge/VS%20Code-Extension-007ACC?logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=superinference.ami-vscode)

**A principled framework for iterative reasoning in large language models**

[Research](#-research) • [Components](#-components) • [Results](#-results)

</div>

---

## 🎯 Overview

**SuperInference** is a feedback-augmented, open architecture for large-language-model (LLM) agents designed for complex programming and multi-step reasoning. The system integrates an explicit planner, a task router, and an embedding-based memory, enabling agents to iteratively refine their actions using execution feedback.

### Key Features

- 🔄 **Event-Driven Architecture**: Sparse, spike-like activation reduces unnecessary computation
- 🧠 **Embedding-Augmented Memory**: Semantic retrieval with noisy channel modeling
- ✅ **Critic-Based Verification**: Precision-gated memory updates ensure quality
- 📊 **Information-Theoretic Evaluation**: Expected Information Gain (EIG) guides reasoning
- 🔧 **Model-Agnostic**: Works with any LLM (OpenAI, Anthropic, Google, DeepSeek, Ollama, OpenRouter)
- 🎨 **Multiple Frontends**: VS Code extension (Marketplace), terminal CLI (releases), OpenClaw plugin (WIP)

---

## 🏆 Results

**SuperInference achieves competitive performance on challenging reasoning tasks:**

- 🥉 **3rd Place** on DABStep leaderboard (Hard Tasks dataset)
- 📈 **12.7% → 41.3%** accuracy improvement on Gemini 2.5 Pro
- ⚡ **Efficient Iteration**: Early rounds extract most valuable information
- 🎯 **Multi-Metric Evaluation**: Accuracy, calibration, drift, and information gain

> *"By treating LLM reasoning as feedback-driven inference with measurable information gain, SuperInference advances both practical reliability and theoretical understanding of interactive AI agents."*

---

## 🧩 Components

### [AMI (Agentic Multi-step Inference)](https://github.com/superinference/ami)

The integrated system built around a shared TypeScript engine with 15 built-in tools:

- **VS Code Extension**: Interactive development environment with chat-driven coding
- **Terminal CLI**: Lightweight REPL interface for scripting and headless workflows
- **OpenClaw Plugin** *(WIP)*: Integration with OpenClaw agents for tool-augmented reasoning

### Core Architecture

```
Planner → Retriever → Executor → Critic → Memory
   ↑                                    ↓
   └────────── Feedback Loop ──────────┘
```

**Event-Driven PRE Loop:**
- **Planner**: Maintains belief state, fires events when EIG ≥ threshold
- **Retriever**: Accesses memory through noisy channel C_η
- **Executor**: Generates candidate actions conditional on context
- **Critic**: Evaluates with error rates (α, β), gates memory updates
- **Memory**: Stores only critic-approved artifacts

---

## 📊 Research

### Published Papers

**SuperInference: Supervised Inference for Partially Observable Environments**

- **Authors**: Carlos Camacho-González, Cristina Catalán-Torrecilla, Luis Llana, Alberto Núñez, Luis Tomás
- **Institutions**: Universidad Complutense de Madrid, Red Hat
- **Year**: 2026
- **Venue**: Software: Practice and Experience
- **DOI**: [https://doi.org/10.1002/spe.0000](https://doi.org/10.1002/spe.0000)

### Key Contributions

1. **Formalization**: POMDP framework with noisy retrieval and verification channels
2. **Information-Theoretic Bounds**: Links retrieval quality, memory updates, and iteration budgets to success
3. **Multi-Metric Evaluation**: Semantic fidelity, calibration, and behavioral stability
4. **Open-Source Implementation**: Complete ecosystem for reproducible research

---

## 🚀 Getting Started

### Quick Start with VS Code Extension

**Option 1: Quick Install (Recommended)**
```bash
curl -fsSL https://www.superinference.org/install.sh | bash
```

**Option 2: Install VS Code Extension from Marketplace**
1. Open VS Code and go to Extensions (`Ctrl+Shift+X` / `Cmd+Shift+X`)
2. Search for "SuperInference" or "AMI"
3. Click Install on the "AMI - SuperInference" extension
4. Open the chat panel (`Ctrl+Alt+P` / `Cmd+Alt+P`) and start coding!

**Option 3: Build from Source**
1. Clone the repository:
   ```bash
   git clone https://github.com/superinference/ami.git
   cd ami
   ```
2. Build the VS Code extension:
   ```bash
   ./scripts/build-vscode-extension.sh
   ```
3. Or build the CLI:
   ```bash
   ./scripts/build-cli.sh
   ```
4. Start the CLI:
   ```bash
   ./scripts/start-cli.sh
   ```

---

## 📚 Documentation

- 🌐 [Project Website](https://superinference.org)
- 📖 [Full Documentation](https://github.com/superinference/ami#readme)
- 📄 [Research Paper](https://doi.org/10.1002/spe.0000)
- 🎓 [Benchmark Results](https://github.com/superinference/ami/tree/main/benchmark/dabstep)

---

## 🔬 Theoretical Foundation

SuperInference formalizes agent operation as a **Partially Observable Markov Decision Process (POMDP)**:

- **Belief State**: Probability distribution over hidden reasoning states
- **Noisy Channels**: Retrieval and critic errors modeled explicitly
- **Information Gain**: EIG threshold determines event firing
- **Convergence Criteria**: Belief concentration, EIG bounds, budget limits

### Key Equations

**Expected Information Gain:**
```
EIG_t = E[H(b_t) - H(b_{t+1})]
```

**Critic Precision:**
```
P(correct|approve) = (1-β)p' / [(1-β)p' + α(1-p')]
```

**Belief Update:**
```
b_{t+1}(s') ∝ Z(o_{t+1}|s',a_t) Σ_s T(s'|s,a_t) b_t(s)
```

---

## 🎯 Use Cases

- **Code Generation**: Multi-file edits with context awareness
- **Debugging**: Iterative refinement with execution feedback
- **Code Review**: Automated analysis with semantic understanding
- **Documentation**: Context-aware explanations and summaries
- **Refactoring**: Safe transformations with validation

---

## 📄 License

This project is licensed under the **GNU General Public License v3.0** - see the [LICENSE](https://github.com/superinference/ami/blob/main/LICENSE) file for details.

---

## 🙏 Acknowledgments

**Institutions:**
- Facultad de Ciencias Físicas, Universidad Complutense de Madrid
- Facultad de Informática, Universidad Complutense de Madrid
- Red Hat (Emerging Partnerships & Ecosystem Engineering)

**Funding:**
This project has received funding from the European Union's Horizon Europe research and innovation programme under grant agreement No 101093129, the Spanish Ministry of Science with projects PID2023-149943OB-I00 and PID2021-122215NB-C31, and the Region of Madrid project TEC-2024/COM-235.

---

## 📈 Performance Highlights

| Metric | Baseline | SuperInference | Improvement |
|--------|----------|----------------|-------------|
| **DABStep Hard** | 12.7% | 41.3% | **+225%** |
| **Leaderboard Rank** | - | **3rd Place** | - |
| **EIG Efficiency** | - | High (early rounds) | Optimal |

---

## 🔗 Links

- 🌐 [Website](https://superinference.org)
- 📦 [VS Code Extension](https://marketplace.visualstudio.com/items?itemName=superinference.ami-vscode)
- 💻 [CLI & Releases](https://github.com/superinference/site/releases/latest)

---

<div align="center">

**Built with ❤️ by the SuperInference Team**

[⬆ Back to Top](#-superinference)

</div>

