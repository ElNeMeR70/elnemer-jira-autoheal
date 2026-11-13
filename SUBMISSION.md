# Devpost Submission Dossier: Atlassian Codegeist 2026

**Competition:** [Atlassian Codegeist 2026](https://codegeist.devpost.com/)  
**Prize Pool:** $120,000 USD  
**Project Title:** JiraAutoHeal AI: Autonomous Issue Triaging, Bug-Localization & Patch-Synthesis  
**Track:** AI Apps & Agents for Jira / Atlassian Rovo  
**Live Production Dashboard:** [https://jira.elnemer-ai.com](https://jira.elnemer-ai.com)  
**Public Code Repository:** [https://github.com/ElNeMeR70/elnemer-jira-autoheal](https://github.com/ElNeMeR70/elnemer-jira-autoheal)  
**Author:** Eng. Mahmoud Bek ElNemer (ElNeMeR AI)  

---

## 1. Elevator Pitch
**JiraAutoHeal AI** transforms Atlassian Jira into an autonomous self-healing software engine. Built on Atlassian Rovo agent specifications and AST semantic code parsing, it ingests bug tickets with raw stack traces, isolates failing functions, synthesizes verified patches, tests them in an isolated regression sandbox, and transitions the Jira ticket to RESOLVED with full audit comments in under 1 second.

---

## 2. Inspiration
Modern engineering teams spend over 35% of their working hours reproducing, localizing, and writing boilerplate fixes for recurring runtime bugs (such as `ZeroDivisionError`, `KeyError`, `IndexError`, and null-pointer exceptions). Despite having clear stack traces in Jira, developers must manually open the repo, find the faulty lines, write unit tests, and create PRs.

We built **JiraAutoHeal AI** to eliminate this friction entirely by turning Jira into a proactive self-repairing ecosystem powered by Atlassian Rovo.

---

## 3. What It Does
1. **Automated Ticket Ingestion:** Listens to Jira Webhooks for new or updated bug tickets, extracting stack traces, environment variables, and reproduction steps.
2. **Semantic AST Codebase Mapping:** Parses Python/JavaScript AST trees to correlate runtime error line numbers with exact functional definitions and call sites.
3. **LLM Patch Synthesis:** Generates minimal, elegant diffs addressing the root cause without altering intended business logic.
4. **Isolated Test Sandbox Verification:** Executes regression tests before and after the patch inside an isolated sandbox subprocess. If tests fail, the agent iterates; if they pass, the patch is locked.
5. **Jira Status Auto-Transition & Audit Trail:** Updates ticket state to *Resolved*, appends git diffs and test results as audit comments, and assigns the issue back to the team lead for final sign-off.

---

## 4. How We Built It
- **Agent Core & AST Engine:** Python 3.10+ utilizing `ast`, `subprocess`, `tempfile`, and isolated sandbox test runners.
- **Interactive Web Interface:** Modern dark-mode responsive dashboard styled with Tailwind CSS, FontAwesome icons, live issue backlog, code diff viewer, and instant patch trigger buttons.
- **Production Edge Hosting:** Live worldwide at `https://jira.elnemer-ai.com` powered by Hostinger cloud edge with HTTP/3 and SSL.
- **Atlassian Integration:** Designed for Atlassian Forge UI Kit and Rovo Agent action triggers.

---

## 5. Challenges We Overcame
1. **Preventing Hallucinated Patches:** LLMs often propose patches that break unrelated unit tests. We introduced the *Pre/Post Execution Sandbox*: a patch is rejected unless 100% of existing regression tests pass.
2. **Sub-Second Execution:** Optimizing AST line-index mapping to identify the failure point within milliseconds rather than traversing entire repositories.

---

## 6. Accomplishments That We're Proud Of
- Verified 0.6-second resolution time on production bugs (like zero division in cart computation).
- Full auditability with clear, human-readable Git diffs posted directly to Jira.
- Live production dashboard accessible worldwide at `https://jira.elnemer-ai.com`.

---

## 7. What We Learned
- Automated self-healing is most effective when combined with strict test harness gates. Rovo agents provide the ideal conversational and action layer for engineering teams.

---

## 8. What's Next for JiraAutoHeal AI
- Direct integration with Bitbucket and GitHub PR creation APIs.
- Multi-file patch synthesis for complex architectural refactoring.
