# javascript-ai-setup

An opinionated starting template for **AI-assisted JavaScript and TypeScript development**, covering **React, Angular, Vue, Svelte, Node.js, and other JavaScript-based projects**.

Start a repository with a consistent set of instructions for how AI should work in your project: where code belongs, which conventions to follow, how to test changes, and what to check before calling the work complete.

This is not a complete application or a framework scaffolder. It provides the repository guidance and configuration that surround your application. You supply the project, its requirements, and its boundaries. Adapted from [MudXtra/dotnet-ai-setup](https://github.com/MudXtra/dotnet-ai-setup).

## Why use it?

AI works better when it does not have to rediscover your project or guess your expectations on every task.

This template gives you a starting point for:

- Keeping changes and additions minimal, without expanding architecture any more than is absolutely necessary.
- Giving AI the project paths and commands it needs to work with less supervision.
- Following test-driven development for behavior changes.
- Reviewing code for correctness, accessibility, security, and maintainability.
- Keeping sensitive data and external databases outside ordinary AI development work.

The defaults reflect the technologies and practices used by the author. They are intentionally opinionated—not an attempt to prescribe the right setup for every JavaScript project.

## Getting started

1. **Create your repository** and copy the starter files from this repository into it.
2. **Create or add your application and tests.** Keep its existing framework and layout, or use the chosen framework’s supported starter for a new application. This template adds no application layers or runtime dependencies.
3. **Configure `PROJECTS.md`** with your actual project paths, responsibilities, protected areas, and verification commands.
4. **Review the defaults** in `AGENTS.md`, the test instructions, and `.editorconfig`. Adapt them to your project before relying on them. This starter does not prescribe a file header; if your project requires one, configure `file_header_template` in the applicable EditorConfig after checking ownership and licensing.
5. **Preserve project configuration.** The root `.editorconfig` covers source, tests, and configuration; merge it with existing settings. Keep the application's own compiler, module, JSX, framework, and build configuration. This template deliberately supplies no universal `tsconfig.json`, bundler configuration, or `package.json`: settings suitable for a browser application may not suit a server or published library.
6. **Keep strict type checking enabled for new TypeScript projects and fail on relevant lint errors; document intentional exceptions in `PROJECTS.md`.** Plain JavaScript projects remain JavaScript. Preserve the existing package manager and its lockfile, and record the actual runtime and framework versions.
7. **Run your documented build and test commands**, then commit the configured starting point.

You can ask AI to inspect your application or packages and draft `PROJECTS.md`. Review the result—especially project responsibilities, protected paths, and commands—before using it as the project map.

## What is included?

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Working rules, development conventions, boundaries, and completion expectations. |
| `PROJECTS.md` | Your repository's project map and targeted verification commands. |
| `AI_REVIEW.md` | A checklist for reviewing changes before submission. |
| `CLAUDE.md` | Loads the shared repository instructions, project map, and review checklist for Claude Code. |
| `.github/copilot-instructions.md` | Directs GitHub Copilot to the shared repository guidance. |
| `.github/instructions/tests.instructions.md` | Testing conventions and regression-test guidance. |
| `.github/pull_request_template.md` | A consistent structure for describing and checking changes. |
| `.editorconfig` | Formatting preferences for source, tests, and configuration. |
| `.gitignore` and `.gitattributes` | Source-control defaults for JavaScript and TypeScript development. |

### One shared setup, framework-specific tools

The shared instructions apply across JavaScript technologies. `PROJECTS.md` records what the actual project uses; framework-specific guidance applies only when that technology is present. A shared instruction template does not mean a single compiler configuration or test command works for every framework.

| Project | How to apply the shared guidance |
| --- | --- |
| React, Next.js, React Native | Preserve the existing React/framework setup, component patterns, renderer, and test utilities. |
| Angular | Preserve Angular CLI/compiler configuration and the configured Angular test entry point and utilities. |
| Vue, Nuxt, Svelte, SvelteKit | Preserve the framework's compiler, component tooling, and test setup. |
| Node.js, other server runtimes, or libraries | Follow the actual runtime, module system, package exports, and existing test runner. |
| Plain JavaScript or TypeScript | Keep the chosen language; apply TypeScript-specific rules only where TypeScript is used. |

Use the existing test runner and assertions. Vitest with its built-in assertions is an option for a new compatible project, not a required migration. Likewise, preserve existing lint and formatting tools rather than adding a second toolchain. See the [React setup guide](https://react.dev/learn/build-a-react-app-from-scratch), [Angular testing guide](https://angular.dev/guide/testing), and [TypeScript configuration reference](https://www.typescriptlang.org/tsconfig/) for technology-specific configuration.

## Make `PROJECTS.md` yours

`PROJECTS.md` connects the general instructions to your actual application. It is not a list of tasks—it tells AI where and how to work.

Replace every placeholder with useful project information:

- The application/package paths and workspace structure, if any.
- The language, framework, runtime, module system, package manager, and relevant configuration paths.
- What belongs in each project.
- Areas that require explicit permission to change.
- Which test projects cover the affected code.
- The commands needed to build, test, and verify changes.

Keep it concise and update it when the project structure or commands change. Do not put credentials, real connection strings, or sensitive application data in it.

A well-maintained project map lets you describe the outcome you want without explaining the repository from scratch each time.

## Working with AI

Once the template is configured, give your AI tool a concrete task and the expected outcome. Ask it to follow `AGENTS.md`, use `PROJECTS.md` to find the right projects and commands, and check its changes against `AI_REVIEW.md`.

For an approved task, end-to-end execution is the default: the agent continues implementation and proportional verification without routine stage pauses. It pauses only at a material boundary or explicit request; scope changes and decisions requiring approval still need your direction.

Repository instructions are guidance, not a security sandbox. Tool support for discovering instruction files varies, so confirm your AI tool is loading the relevant guidance. Review the resulting changes and verification evidence before accepting them.

The external-database boundary is defined in [AGENTS.md](AGENTS.md#external-database-boundary). Development and tests should use permitted local, synthetic data—not external databases or copies of real customer or production data.

## Using the files in an existing repository

Starting a new project is the primary use, but you can also adapt these files to an existing repository. Review and merge its existing instructions and configuration rather than assuming the template should replace them.

Copy the files you need manually, preserve your repository-specific settings, and configure `PROJECTS.md` with the existing project structure and commands.

## License

This template is provided under the [MIT License](LICENSE).
