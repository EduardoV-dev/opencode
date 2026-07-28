# General Testing

- Design code with explicit boundaries so network, storage, time, processes, and other external
  effects can be replaced in tests.
- Test observable behavior and public contracts, not private implementation details.
- Add a regression test for a bug fix when practical, especially at the boundary where the bug was
  introduced.
- Mock external systems at their boundary; do not mock internal functions merely to make a test pass.
- Keep tests deterministic, readable, isolated, and colocated with the code they protect when the
  repository convention allows it.
- Prefer user-visible or semantic selectors in interface tests over implementation details.
- Cover authorization failures, invalid input, unsafe input, failure paths, and important edge cases
  in addition to the happy path.
- Do not create a test suite, fixture layer, or mock abstraction for trivial code with no meaningful
  behavior; test effort should follow risk.
