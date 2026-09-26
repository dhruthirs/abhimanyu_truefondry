# Secret-Leak Guardian Demo

## Problem

Developers can accidentally commit API keys, passwords, tokens, or private keys into GitHub repositories.

Secret-Leak Guardian helps detect these leaks and safely guide the developer through remediation.

## Demonstrated Flow

```text
Authorized GitHub Repository
            ↓
      Secret Detection
            ↓
   Classification & Analysis
            ↓
       Risk Assessment
            ↓
      Human Approval
            ↓
     Remediation Branch
            ↓
       Commit Changes
            ↓
      Pull Request
            ↓
      Re-scan & Verify
