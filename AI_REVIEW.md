# AI_REVIEW.md - Pull request and general code change review checklist

Use this checklist before proposing or accepting code changes.

## Scope

* confirm the change stays within the requested task
* confirm no unrelated refactors or file moves were introduced
* confirm protected projects were not modified unless explicitly requested
* distinguish identifying a rule needing revision from authority to silently violate it

## Architecture

* confirm logic is placed in the correct project
* confirm new abstractions are necessary and fit existing patterns
* confirm dependency direction remains appropriate

## Security and data handling

* confirm no secrets, tokens, passwords, certificates, private URLs, or real connection strings were added
* confirm sensitive data is not logged, exposed, or copied into examples or tests
* confirm configuration changes are safe for local, CI, and production use

## JavaScript, TypeScript, and UI rules

* confirm the existing framework, runtime, module system, and package manager are preserved unless the task requires a change
* confirm compiler and build configuration fit the actual runtime and framework
* confirm component, state, lifecycle, and styling patterns fit the existing project without unnecessary architecture additions
* confirm accessibility remains intact for interactive UI, including keyboard support and ARIA expectations

## Testing

* confirm a focused test was added or updated when behavior changed
* confirm tests use the repository's existing runner, assertions, and framework test utilities
* confirm UI tests re-query elements after interactions where references can become stale
* confirm tests await async operations and use async interaction helpers where applicable
* confirm tests do not use unnecessary delays or brittle timing
* confirm test names follow repo naming conventions

## Code quality

* confirm the diff is minimal and readable
* confirm JSDoc/TSDoc exists for new exported APIs
* confirm no warnings were suppressed to force success
* confirm no unnecessary dependencies were introduced
* confirm hard-coded colors were not added to interactive UI

## Verification

* confirm any suggested commands are targeted to the affected package or app, not the whole workspace, unless explicitly requested
* confirm formatting guidance is scoped to changed files when possible
* confirm the consumer is told about any critical problems that were found

## Output expectations

* keep feedback brief and actionable
* separate required fixes from optional suggestions
* call out critical problems explicitly
* do not request unnecessary cleanup outside the task scope
