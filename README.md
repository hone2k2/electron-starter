# Electron Starter

Desktop application built with [Electron](https://www.electronjs.org/),
[React](https://react.dev/), and TypeScript. The project uses
[electron-vite](https://electron-vite.org/) to develop and package the renderer,
main process, and preload script.

## Tech Stack

- **Desktop runtime:** [Electron 39](https://www.electronjs.org/)
- **UI:** [React 19](https://react.dev/) and React DOM
- **Language:** [TypeScript 6](https://www.typescriptlang.org/)
- **Build tooling:** [Vite 7](https://vite.dev/) and [electron-vite](https://electron-vite.org/)
- **Styling:** [Tailwind CSS 4](https://tailwindcss.com/)
- **Packaging:** [electron-builder](https://www.electron.build/)
- **Electron utilities:** `@electron-toolkit/preload`, `@electron-toolkit/utils`, and [electron-updater](https://www.electron.build/auto-update)
- **Code quality:** [ESLint](https://eslint.org/) and [Prettier](https://prettier.io/)

## Requirements

- Node.js compatible with Electron 39
- Yarn or npm
- macOS, Windows, or Linux to build the corresponding package

## Getting Started

Install the dependencies:

```bash
yarn
```

Start the application in development mode:

```bash
yarn dev
```

Press `F12` in the application window to open DevTools.

## Common Commands

| Command             | Description                              |
| ------------------- | ---------------------------------------- |
| `yarn dev`          | Run the application in development mode  |
| `yarn build`        | Type-check and build the application     |
| `yarn start`        | Run the built application with Electron  |
| `yarn lint`         | Check the source code with ESLint        |
| `yarn format`       | Format the source code with Prettier     |
| `yarn typecheck`    | Type-check the main process and renderer |
| `yarn build:unpack` | Build an unpacked application directory  |
| `yarn build:mac`    | Build the macOS package                  |
| `yarn build:win`    | Build the Windows package                |
| `yarn build:linux`  | Build the Linux package                  |

Build files are generated in `dist/` or `out/`, depending on the build step.

## Project Structure

```text
src/
├── main/                 # Electron main process
├── preload/              # Secure APIs shared with the renderer
└── renderer/
	├── index.html
	└── src/
		├── App.tsx       # Root UI component
		├── components/   # React components
		└── assets/       # CSS and UI assets
```

The `main` process manages the Electron window lifecycle and application-level
events. The `preload` script provides the IPC bridge for the renderer. The React
UI lives in `renderer` and does not access sensitive Node.js APIs directly.

## Pre-build Checks

```bash
yarn lint
yarn typecheck
yarn build
```

## Recommended Tools

- [Visual Studio Code](https://code.visualstudio.com/)
- [ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
