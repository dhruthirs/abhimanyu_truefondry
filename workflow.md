# Secret-Leak Guardian Workflow

The agent follows a controlled workflow from detection to verification.

## 1. Detection

The agent uses GitHub tools to inspect authorized repository files and identify credential-like values.

Examples include:

- API keys
- Access tokens
- Passwords
- Private keys
- Cloud credentials

## 2. Classification

Each finding is classified using:

- Secret type
- Severity
- File location
- Detection pattern
- Repository context

The agent also checks whether the value appears to be a real credential, placeholder, or intentionally created test value.

## 3. Investigation

The agent investigates the surrounding file and, when required, relevant repository history.

The purpose is to understand:

- Where the value appeared
- How it was introduced
- Whether it is still present
- Whether repository context suggests a test or real credential

Complete secret values are never included in the report.

## 4. Risk Assessment

The agent prepares a short risk assessment containing:

- Finding
- Severity
- Evidence
- Potential impact
- Recommended remediation

## 5. Human Approval

Before making repository changes, the agent presents the finding and proposed remediation to the user.

The agent waits for explicit approval.

No approval is assumed.

## 6. Remediation

After approval, the agent:

1. Creates a separate remediation branch.
2. Updates the affected file safely.
3. Creates a commit.
4. Opens a pull request against the main branch.

The main branch is not modified directly.

## 7. Verification

After remediation, the agent performs another read-only scan of the affected file.

The verification checks whether the previously detected credential-like values are still present.

## 8. Final Result

The workflow ends with a clear status:

```text
Secret Detected
      ↓
Risk Assessed
      ↓
Human Approved
      ↓
Remediation Completed
      ↓
Pull Request Created
      ↓
Secret Re-scanned
      ↓
Remediation Verified
