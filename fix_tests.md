# Fixing Tests

**Reference:** See `convention.md` for general coding standards.

Work through failing tests one at a time. Pick one to start.

Analyze the failure and explain if it is due to:

1.  **Incomplete code:** Functionality hasn't been implemented yet.
2.  **A bug in the code:** The implementation is incorrect.
3.  **Out-of-date testing:** The test no longer reflects the requirements.
4.  **Inconsistent business rules:** The requirements themselves are
    contradictory.

**NO CODE CHANGES** until I agree with your proposal.

When fixing bugs it is critical to consider the root cause and fix that. If a key is missing do not simply create a default in the local code. Ask, where is this key supposed to come from? Why is it missing? What is the best way to fix it?
