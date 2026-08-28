# learn-react

A scratchpad for learning React.js, JavaScript, TypeScript and  other related frameworks.

## Dev Container

This repo ships a [Dev Container](https://containers.dev/) definition in [.devcontainer/devcontainer.json](.devcontainer/devcontainer.json).

Open the folder in VS Code and run **Dev Containers: Reopen in Container**, or use the CLI:

```sh
devcontainer up --workspace-folder .
```

- Base image: `mcr.microsoft.com/devcontainers/typescript-node:26-trixie` (Node 26, matching `engines.node`)
- pnpm is provisioned by Corepack from the `packageManager` field in `package.json`
- `node_modules` and the pnpm store live in named volumes, so host and container installs never mix
- `pnpm dev` serves on port **5173** and `pnpm preview` on **4173**; both are forwarded automatically

---

This template provides a minimal setup to get React working in Vite with HMR and some Oxlint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the Oxlint configuration

If you are developing a production application, we recommend enabling type-aware lint rules by installing `oxlint-tsgolint` and editing `.oxlintrc.json`:

```json
{
  "$schema": "./node_modules/oxlint/configuration_schema.json",
  "plugins": ["react", "typescript", "oxc"],
  "options": {
    "typeAware": true
  },
  "rules": {
    "react/rules-of-hooks": "error",
    "react/only-export-components": ["warn", { "allowConstantExport": true }]
  }
}
```

See the [Oxlint rules documentation](https://oxc.rs/docs/guide/usage/linter/rules) for the full list of rules and categories.
