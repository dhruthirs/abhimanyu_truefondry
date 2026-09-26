# Secret-Leak Guardian — Agent Configuration

## 1. Agent Overview

**Agent Name:** Secret-Leak Guardian

**Purpose:**  
An AI-powered security agent that detects exposed credentials in authorized GitHub repositories, analyzes their risk, requests human approval, safely remediates the issue, and verifies the result.

**Agent Runtime:** TrueForge

**AI Model:** OpenAI

**Repository Integration:** GitHub MCP Tools

---

## 2. Problem

Developers can accidentally commit sensitive information such as:

- API keys
- Access tokens
- Passwords
- Private keys
- Cloud credentials
- Other credential-like values

These secrets can remain hidden inside configuration files or source code.

Secret-Leak Guardian automates the investigation and remediation workflow while keeping the developer in control of repository changes.

---

## 3. Core Workflow

The agent follows:

**Detect → Classify → Investigate → Assess Risk → Request Approval → Remediate → Verify**

```text
GitHub Repository
       |
       v
Secret Detection
       |
       v
Classification
       |
       v
Investigation
       |
       v
Risk Assessment
       |
       v
Human Approval
       |
       v
Remediation Branch
       |
       v
File Update
       |
       v
Commit
       |
       v
Pull Request
       |
       v
Re-scan
       |
       v
Verification
