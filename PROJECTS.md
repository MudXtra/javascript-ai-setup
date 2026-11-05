# Project boundaries

## First-use project map workflow
PROJECTS.md is a maintained map of verified facts, not a task list or source of new permission. Inspect the existing application or package first and record its framework, language, runtime, module system, package manager, workspace layout, roles, test mapping, protected areas, and verified commands. For an empty repository, propose the smallest layout matching the chosen application and obtain approval for material structure decisions. UI, data, and separate test roles may be `N/A`; never create a package merely to satisfy a placeholder. Never record secrets, real connection strings, or sensitive data.

This starter has no application implementation, package manifest, installed tools, or runnable build/test target. Configure and verify the entries below in the consuming repository.

## Files and paths
- {{PACKAGE_OR_APP_PATHS}} identifies the application/package roots and relevant `package.json` files
- {{STACK}} records JavaScript or TypeScript, framework and versions, runtime and version, module system, package manager and version
- {{CONFIG_PATHS}} identifies compiler, framework, build, test, lint, and formatting configuration
- {{SOURCE_PATHS}} owns application or library implementation
- {{UI_PATHS}} owns components/pages/assets/interaction logic; N/A is allowed
- {{DATA_PATHS}} owns persistence/services/data access; N/A is allowed
- {{TEST_PATHS}} owns tests and records which application/package they cover
- {{PROTECTED_PATHS}} allows N/A; do not edit unless explicitly instructed

## Verification prerequisites and evidence
Run commands from the repository root unless a documented command names another working directory. Before running a command, verify the package's scripts, tool versions, test runner, paths, and any workspace selector. Run a focused test before the full package tests when it applies. Use broader workspace validation only when the change, dependency, shared setting, or workspace wiring justifies it.

In the final report, name every command actually run and its outcome. Name relevant checks not run, explain why they were not run or not applicable, and never imply a build or test ran when this project map has no runnable target.

## Targeted commands

Replace this table with actual verified commands, including the working directory and workspace selector when needed. Use the existing package manager and retain its lockfile. Do not copy flags between runners: an Angular CLI test target, a direct Vitest script, a Jest script, and Node's test runner take different options.

| Check | Record here |
| --- | --- |
| Focused test | {{FOCUSED_TEST_COMMAND}} |
| App/package tests | {{TEST_COMMAND}} |
| Type checking, if configured | {{TYPECHECK_COMMAND_OR_NA}} |
| Lint | {{LINT_COMMAND_OR_NA}} |
| Build, if applicable | {{BUILD_COMMAND_OR_NA}} |
| Format changed files | {{FORMAT_COMMAND}} |
| Browser/UI verification, if relevant | {{BROWSER_CHECK_OR_NA}} |

For example, `npm run build` is applicable only if that package defines a build script. Record the existing framework's test entry point rather than bypassing its setup. Do not create build, typecheck, or lint scripts merely to fill an `N/A` entry.
