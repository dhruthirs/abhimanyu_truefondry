# Test Cases

Secret-Leak Guardian was tested using intentionally fake credentials in an authorized GitHub test repository.

## Test Case 1 — Repository Access

**Repository:** `dhruthirs/abhimanyu_truefondry`

**Result:** Passed

The agent successfully accessed the authorized repository using GitHub MCP tools.

---

## Test Case 2 — Secret Detection

**File:** `test-secrets.env`

**Result:** Passed

The agent detected multiple credential-like values including API keys, passwords, access tokens, and a private key.

All detected values were intentionally fake test credentials.

---

## Test Case 3 — Classification and Masking

**Result:** Passed

The agent classified the detected findings by type, severity, file location, and context.

Secret values were kept masked and were not exposed in the final report.

---

## Test Case 4 — Human Approval

**Result:** Passed

The agent stopped before making repository changes and requested explicit user approval.

No repository modification was performed before approval.

---

## Test Case 5 — Remediation

**Branch:** `permission-test`

**Result:** Passed

After approval, the agent:

1. Created a separate remediation branch.
2. Replaced the detected fake credentials with safe placeholders.
3. Created a commit.
4. Created a pull request for review.

**Commit:** `1dedec6b1f328669ba05b48076bf363811e15f34`

**Pull Request:** #1

---

## Test Case 6 — Post-Remediation Verification

**Result:** Passed

The agent re-scanned the affected file after remediation.

The previously detected credential-like values were no longer present.

The remediation was successfully verified.

---

## Overall Test Result

**All MVP test cases passed.**

The demonstrated workflow is:

**Detect → Classify → Investigate → Human Approval → Remediate → Commit → Pull Request → Re-scan → Verify**

No real production credentials were used during testing.
