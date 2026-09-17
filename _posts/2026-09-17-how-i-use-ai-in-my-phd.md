---
layout: post
title: "How I Actually Use AI in My PhD: A Practical Guide"
date: 2026-09-17 20:30:00 -0300
author: Anderson Nunes
tags: [phd, artificial-intelligence, research, mechanical-engineering, productivity]
---

Recently, my friend **Breno Dyego** asked me a straightforward question:

> *"Anderson, how do you actually use AI in your day-to-day PhD research? What does your actual workflow look like?"*

Breno's question hit the mark because there is an enormous chasm between the popular perception of AI in academia and what it looks like to do **scientific research powered by agentic AI systems**.

For most people, "using AI in graduate school" still sounds like opening a ChatGPT browser tab to fix English grammar in an abstract or asking for a high-level summary of a PDF. While handy, that is barely scratching the surface.

In my case—pursuing a PhD in Mechanical Engineering at **PPGEM/UFRN** (focusing on computational radiative heat transfer, spectral gas–liquid coupling, numerical solvers, and an international cotutelle in Germany)—the work revolves around rigorous mathematical physics: integro-differential equations (such as the Radiative Transfer Equation, or RTE), numerical stability, boundary layer phenomena, and scientific programming. In computational physics, there is zero tolerance for hallucinations.

Here is a breakdown of how I structured this **new way of doing a PhD**.

---

### 1. The End of "Solitary Coding": AI as a Scientific Pair Programmer

Scientific programming has a notoriously unforgiving learning curve. Implementing numerical methods (Monte Carlo, discrete ordinates, finite volumes) requires translating dense analytical formulations into efficient code without introducing subtle discretization or indexing bugs.

Instead of coding in isolation:
- **Implementation with Verification Plans:** When writing new modules for a solver (whether in Python, C++, or modernizing legacy Fortran routines), I have the agent generate mathematical unit tests and boundary-condition checks in parallel.
- **Analytical & Numerical Cross-Checks:** If I am testing a 3D convolution or an anisotropic scattering solver, I ask the agent to derive the corresponding 1D analytical limit or assemble a benchmark script (e.g., comparing a Monte Carlo implementation against a canonical literature solution).
- **Hunting Bottlenecks and Vectorization:** The AI assists in profiling nested loops, identifying memory transfer overheads, or optimizing routines with Numba/GPU libraries while strictly preserving mathematical equivalence.

The golden rule here: **I never accept code without an automated validation plan**. The AI accelerates syntax and boilerplate; the physical checks (conservation of energy, residual convergence) decide if the code is correct.

---

### 2. The Connected Ecosystem: Model Context Protocol (MCP) and Local Tools

The true leap forward from a web chatbot to a serious research environment is **MCP (Model Context Protocol)** and tool execution capabilities.

In my setup, the AI models do not live in an isolated browser window. They are integrated directly into my development environment:

1. **Academic Library via Zotero MCP:** My local Zotero library (containing hundreds of tagged and annotated papers) is directly queryable. When I need to recall how a specific group parameterized the spectral absorption coefficient in a 2018 paper, the agent retrieves the exact entry and notes from my collection.
2. **Terminal & Test Runners:** The agent can execute validation scripts, inspect stdout/stderr logs, detect where residuals begin to diverge, and propose targeted fixes right in the solver repository.

---

### 3. Persistent Memory: Defeating Context Decay

A PhD spans several years. Over that time, you make thousands of micro-decisions:
- *"Why did we choose a 16-point Gauss-Legendre quadrature instead of 8?"*
- *"What was the theoretical justification for discarding a gray-gas assumption in the pool fire model?"*
- *"What were the exact scope agreements established for the international cotutelle?"*

Relying solely on human memory or scattered notes leads to painful context loss.

I use a **shared local memory system (`ai-memory`)**. Durable decisions, validated mathematical formulations, and project parameters are logged into structured pages. When returning to a solver problem months later, the AI retains the verified chain of reasoning, eliminating the need to re-explain the project from scratch.

---

### 4. Literature Review with Strict Provenance

Rigorous science cannot tolerate fabricated citations or vague summaries. My literature workflow follows three non-negotiables:

- **Direct Academic APIs:** Searches run against real scholarly databases (OpenAlex, Crossref, arXiv, PubMed).
- **Local PDF Inspection:** The agent extracts text directly from full-text PDFs on my drive, focusing on exact methodology sections rather than guessing.
- **Socratic Debate & Rival Hypotheses:** The AI's greatest strength is acting as a sounding board. When confronted with an unexpected physical readout, I can ask: *"What competing mechanisms in radiative transfer or kinetics could explain this non-exponential attenuation profile?"*.

---

### 5. The Core Philosophy: Cognitive Amplification, Not Thought Outsourcing

The fundamental question every researcher should ask is: **Is the AI eliminating mechanical friction, or is it replacing your own thinking?**

- If you use AI to outsource understanding, you defeat the purpose of a doctorate. You become an operator who will crumble under questioning at your thesis defense.
- But if you use AI to **eliminate syntactic and bureaucratic friction**—writing test harnesses, cross-referencing papers, automating plots and pipeline checks—you gain something priceless: **high-bandwidth cognitive time to think about the underlying physics**.

The PhD didn't become easier; it became **much deeper**. With the right tools, I can test more hypotheses, simulate more configurations, and refine models far more thoroughly in a single week than would have been possible in a month of manual boilerplate.

---

### Takeaways for Breno (and Anyone Starting Out)

If you want to adopt this approach in your own research:

1. **Bring AI to your files:** Move away from copy-pasting into web chats. Use IDE-integrated agents that can inspect your scripts and data directory.
2. **Connect your knowledge:** Hook up your literature manager (like Zotero) to your agentic tools.
3. **Never compromise on rigor:** Don't accept a formula or a code snippet you cannot derive yourself. Use the AI to explain the *why*, and always verify against ground truth.

This is the new paradigm of scientific research. And we are just getting started.
