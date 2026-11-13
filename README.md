# 🛠️ JiraAutoHeal AI: Autonomous Bug-Triaging & Patch-Synthesis Agent

[![Atlassian Codegeist 2026](https://img.shields.io/badge/Atlassian-Codegeist%202026-0052CC?logo=atlassian&logoColor=white)](https://codegeist.devpost.com)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Rovo Agent Compatible](https://img.shields.io/badge/Atlassian-Rovo%20Agent-36B37E.svg)](https://www.atlassian.com/software/rovo)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)

Official Submission for **Atlassian Codegeist 2026 ($120,000 Hackathon)**.

**Author:** Eng. Mahmoud Bek ElNemer (`ElNeMeR70`)  
**Affiliation:** ElNemer AI Systems & Research

---

## 📌 Problem Statement & Architecture

Modern software engineering teams spend over 35% of sprint velocity reproducing runtime exceptions, correlating cryptic stack traces, and writing trivial defensive guard patches.

**JiraAutoHeal AI** transforms Jira from a passive issue tracker into an **autonomous self-healing software engineer**:
1. **Webhook Ingestion:** Detects new bug reports with attached crash logs or Sentry traces.
2. **AST-Correlated Bug Localization:** Pinpoints the exact failure line inside multi-file codebases.
3. **Defensive Patch Synthesis:** Synthesizes minimal-footprint, non-breaking Git patches.
4. **Sandboxed Verification:** Back-tests patches against unit test suites before transitioning ticket status to `RESOLVED`.

---

## 🚀 Live Demo & Usage

### 1. Launch the interactive dashboard:
Simply open `index.html` in any browser or run:
```bash
python jira_agent.py
```

### 2. Features:
* **Interactive Ticket Backlog:** Inspect critical, high, and medium runtime bugs.
* **Real-Time Agent Terminal:** Watch the AI analyze ASTs and synthesize code in under 1 second.
* **Visual Git Diff Viewer:** Clean side-by-side inspection of repaired code before merging.

---

## 📄 License
Licensed under the **Apache License 2.0**.
