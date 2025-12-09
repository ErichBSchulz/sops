cat << 'EOF' > making_plans.md
# Making Plans

When asked to make a plan, generate a `PLAN.md` (or update the existing one) using the following convention.

## 1. Context & Goal
* **Goal:** A 1-sentence summary of what we are achieving.
* **Constraints:** (e.g., "No external libraries," "Python 3.10 only").
* **Current State:** A brief note on the starting point.

## 2. Outstanding Questions (Discovery)
Identify unknowns before planning.
- [ ] Question 1...
- [ ] Question 2...


**STOP:** If there are questions in this section, stop and ask me before proceeding to detailed planning.

## 3. The Plan
Break work into "Phases" (100, 200, etc.) to facilitate inserting items later.
* **Notation:** * `- [ ]` = To Do
    * `- [x]` = Done
    * `- [!]` = Blocked/Failing

**Format for every step:**
* **Phase 100: [Phase Name]**
    - [ ] **110**: [Information gathering]
        - Consider what files you would like to see. Consider running commands such as `rg keyword tests` or `rg keyword /src/modules -C 5` etc.
    - [ ] **120**: [Actionable Step Description]
        - *Verification:* [Specific command/test to prove it works, e.g., `pytest tests/test_auth.py` or `curl localhost:8000`]
    - [ ] **130**: ...

## 4. Execution Rules
1.  **Iterative Mode:** Perform one step at a time.
2.  **Confirm Completion:** After finishing a step, run the *Verification* command. Ask me: "Step X is complete. Verification passed. Shall I move to Y?"
3.  **No Zombie Code:** If a step fails, do not comment it out. Fix it or mark the task `[!]` (Blocked).

## 5. Close Out
Once all phases are `[x]`, perform the close-out routine:
1.  Update README and other related documents with key information (if any).
2.  Final confirmation that all tasks are complete and permission granted to remove debug code.
3.  Remove debug code.
4.  Final confirmation code executes.
EOF
