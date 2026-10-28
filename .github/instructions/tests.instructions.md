---
applyTo: "tests/**"
---

# Test Instructions

- Unit tests call service functions with `MagicMock` repositories; do not use a database or HTTP.
- Test one behavior per test, naming tests `test_<function>_<situation>`.
- For a bug fix, first write a test that fails on the current code.
- Never weaken or delete an existing assertion; stop and ask instead.
