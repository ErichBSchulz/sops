# Logging Cleanup and Standards

**Reference:** See `convention.md` for general coding standards.

**Analysis:**

- Analyze existing logging before making changes.

**Cleanup:**

- Remove all temporary `BUG` tags and related comments (e.g., `BUG20250705`).
- Remove unneeded logging that adds no value (noise).

**Retention & Levels:**

- **DEBUG:** Keep key messages that capture hard-to-access internal logic and
  inputs/outputs.
- **INFO:** Upgrade key summary logs to "INFO" level.
- **WARNING/ERROR/CRITICAL:** All unhappy path logic must be graded as WARNING,
  ERROR, or CRITICAL.

You may upgrade a log intensity but NEVER downgrade a log intensity unless
specifically instructed.

If logging rules are unclear, ask for clarification.
