# agent-squash
Agent-Squash is aimed to be an autonomous agentic pipeline designed with a singular purpose: reproducing and fixing software bugs.

## 🛠 The Architecture
agent-squash operates as a linear progression of specialized subagents. 
PoC is planned be interactive in Cursor.

### 1. The Extractor 
Input: JIRA Bug URL.

Action: Distills unstructured "human" reports into a machine-readable Bug Manifest.

Output: Structured JSON (Reproduction steps, expected vs. actual).

### 2. The Reproducer
Input: Bug Manifest.

Action: Checks environments (Dev/Stage/Prod) to execute reproduction scripts.

Output: 
- Structured JSON (Bug Manifest with Reproducibility Matrix) 
- Reproducer script (playwright)

### 3. The Fixer
Input: Bug Manifest with Reproducibility Matrix + Source Code access.

Action: Performs Root Cause Analysis (RCA) and generates a patch.

Output: Pull Request confirmed by failing reproducer test.
