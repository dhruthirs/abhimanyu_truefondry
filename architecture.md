# System Architecture

Secret-Leak Guardian is built around a TrueForge AI agent connected to GitHub through MCP tools.

## Architecture

```text
                    User
                     |
                     v
             TrueForge Agent
                     |
             +-------+-------+
             |               |
             v               v
        Gemini Model     GitHub MCP
             |               |
             |               v
             |        GitHub Repository
             |               |
             +-------+-------+
                     |
                     v
              Secret Analysis
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
              Commit Changes
                     |
                     v
               Pull Request
                     |
                     v
            Post-Remediation Scan
                     |
                     v
                Verification
