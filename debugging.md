# Debugging IMPORTANT

**Reference:** See `convention.md` for general coding standards.

Use this pattern for running tests to filter relevant logs:

    source .venv/bin/activate && pytest tests/unit/test_checkin_dimension_value_reception.py::test_dimension_observation_recorded_to_module -v -s --log-cli-level=DEBUG 2>&1 | grep -E "(taga|tagb|INFO|WARNING|ERROR|CRITICAL|PASSED|FAILED)"

You can add specific file names or keywords as tags in the grep pattern to
isolate high-value information.

**Logging Strategy:**

- Prefer adding debug logs to test files first.
- Only add logging to production code if test logs are inadequate.

**Debug Protocol:**

1.  **Step-by-Step:** When asked to `debug`, proceed carefully one step at a
    time.
2.  **Assumptions:** Never assume you have found the problem. Assume you have
    found a _potential_ problem. Verify all assumptions by inspecting files (use
    `cat`, `grep`).
3.  **Communication:**
    - Start every response in a debug session with `[debug mode]`.
    - Never say "I have found the problem." Say "I might have found the
      problem."
    - We stay in debug mode until _I_ say it is finished.
4.  **Changes:**
    - Other than adding debug logging, make _only_ one change at a time.
    - Do _not_ change code unless asked.
    - Do _not_ attempt to `fix` the bug until explicitly asked. Focus 100% on
      diagnosis.

**Instrumentation:**

- Liberally increase logging.
- Use a temporary tag in the form `BUGYYYYMMDD` (e.g., `BUG20250705`) in log
  messages and comments to simplify cleanup and filtering.
- Example: `log.debug("BUG20250705 variable x value: %s", x)`

**Extreme Debugging:**

- It is acceptable to use try/except blocks to probe configurations.
- If an approach fails, comment it out rather than deleting it immediately.
- Wrap temporary debug blocks:
  ```python
  # BUG20250705START
  # ... debug code ...
  # BUG20250705END
  ```

**Verification:**

- Before suggesting changes, ask: "Have I verified the input variables?" and
  "Are the files as I expect?"
- Use log inspection, `cat`, and `grep` to verify reality.
- Do not propose fixes until the current situation is fully verified.
- Only clean up debug code when the bug is resolved _and_ you are asked to do
  so.
