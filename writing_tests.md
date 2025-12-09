# Writing Tests

**Reference:** See `convention.md` for general coding standards.

Write DRY tests that make the business logic being tested explicit.

Use existing test harnesses. Pay attention to the contents of `tests/helpers`.

Start simple. If future tests are obvious, suggest them using 'TODO:' tags in
the files.

Explain why each assertion is important in comments if not immediately obvious.

Avoid asserting on exact wording strings; rely on intent and pattern matching
(e.g., regex) to make tests less brittle.
