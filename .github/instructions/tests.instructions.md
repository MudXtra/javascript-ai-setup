---
applyTo: "**/*.test.{js,jsx,ts,tsx,mjs,cjs,mts,cts},**/*.spec.{js,jsx,ts,tsx,mjs,cjs,mts,cts},**/{tests,test,__tests__}/**/*.{js,jsx,ts,tsx,mjs,cjs,mts,cts}"
---
# Test instructions

Use these rules for test work. Keep tests small, deterministic, and behavior-focused.

Use the repository's existing runner, assertions, and framework test utilities. Vitest with its built-in assertions is a starting option for a new project when compatible with its framework; do not replace an existing test stack or add test dependencies without approval.

## Do / Don't (Read First)

### Do
- keep tests in the paths defined in `PROJECTS.md`; preserve colocated tests or existing test directories
- use plain unit tests for logic and framework test utilities for components, routing, rendering, or framework-managed services
- prefer the simplest test type that verifies the behavior
- test observable output, interactions, and results, not framework or component internals
- re-query DOM elements after interactions where references can become stale
- use the framework's renderer or change-detection helpers where required
- await async operations and prefer async interaction helpers where applicable
- register only the minimal required test doubles
- mock or fake network clients, navigation, time, and external services as needed
- prefer targeted assertions on text, attributes, enabled or disabled state, validation messages, CSS classes, and callback results
- use TDD for behavior changes: start with a failing test
- keep tests isolated and deterministic
- use the runner's fake timers or event-driven gates instead of fixed sleeps
- restore mocks, timers, and environment changes after each test
- ensure test names clearly describe the behavior being verified

### Don't
- do not create a separate test package unless repository structure or maintainability requires it
- do not use broad snapshot assertions when targeted assertions are enough
- do not test third-party library internals directly
- do not use live network calls, real external services, or unnecessary filesystem access
- do not put secrets or sensitive data in fixtures or sample inputs
- do not end test names with `Test` or `Async`
- do not include `Test_` in test names
- do not end test names with `_`

## Test project structure

Use colocated tests or the existing test directory recorded in `PROJECTS.md`. Do not introduce additional layers just to organize tests.

## Regression testing

- For each behavior bug fix, write a failing test first that captures the defect scenario and expected behavior.
- Keep at least one targeted assertion tied to the historical bug symptom.
- Preserve nearby existing behavior checks to reduce regression risk.
- Avoid broad refactors; prefer minimal, behavior-preserving test additions and fixes.
- When the consuming project uses an issue tracker, record its identifier in that project’s convention; otherwise retain a targeted assertion tied to the historical symptom.

## Verification

Use `PROJECTS.md` for project-specific verification paths and commands. Runner flags differ: do not pass Vitest flags to Angular CLI, Jest, or another runner without checking the configured command.
