# Secret-Leak Guardian

Secret-Leak Guardian is an AI-powered security agent built using TrueForge to detect exposed credentials in authorized GitHub repositories, understand their risk, and help developers fix them safely.

## Problem

Developers sometimes accidentally push sensitive information such as API keys, passwords, access tokens, or private keys into GitHub repositories. Finding these leaks manually can be difficult, especially when they are buried inside configuration or source files.

Secret-Leak Guardian helps automate this process while keeping the developer in control of any changes made to the repository.

## How It Works

The agent works with an authorized GitHub repository and follows a simple workflow:

1. Scans repository files for possible secrets.
2. Identifies the type and severity of each finding.
3. Checks the surrounding file and repository context.
4. Keeps detected secret values masked in its reports.
5. Explains the risk and suggests how to fix it.
6. Asks the user for approval before making any changes.
7. Creates a separate remediation branch.
8. Replaces the exposed value with a safe placeholder.
9. Creates a pull request for review.
10. Scans the updated file again to confirm that the issue has been fixed.

## Architecture


        GitHub Repository
                |
                v
        TrueForge AI Agent
                |
                v
       Secret Detection
                |
                v
     Classification & Analysis
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
        Commit + Pull Request
                |
                v
      Post-Remediation Scan
                |
                v
        Verification Report
