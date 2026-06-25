# Session Forge Browser

> A multi-account browser session manager for running isolated Gmail, Slack, and web accounts side by side in named workspaces.

Session Forge Browser helps you stay signed in to multiple accounts on the same website at the same time. Each profile runs in a fully isolated browser session with its own cookies, storage, cache, and session data, so your work, personal, and client accounts stay completely separate.

## Features

* **Isolated sessions** — each profile has separate cookies, localStorage, cache, and session data
* **Customizable profiles** — name each profile, choose from 400+ icons, upload a custom image, and assign a color
* **Per-profile language settings** — configure the browser language individually for each profile, with support for 15 languages
* **Notification control** — manage notifications per profile with Allow all, Ask, or Block all options, and clearly see which profile each alert belongs to
* **Collapsible sidebar** — switch between icon-only and icon + name views for a cleaner workspace
* **Drag-and-drop ordering** — organize profiles in the order that fits your workflow
* **Data management** — clear cookies, cache, and app data for individual profiles without affecting others
* **Crash recovery** — reload unresponsive or crashed sessions without restarting the entire app
* **Lightweight experience** — built with Electron and optimized for fast profile switching

## Technology Stack

| Layer            | Choice                          |
| ---------------- | ------------------------------- |
| Framework        | Electron                        |
| Build tool       | electron-vite                   |
| UI               | React + TypeScript              |
| Styling          | Tailwind CSS                    |
| Persistence      | electron-store                  |
| Package manager  | Yarn                            |
| Runtime          | Node.js 24 LTS                  |

## Getting Started

### Prerequisites

- Node.js 24 LTS
- Yarn

A [VS Code](https://code.visualstudio.com/) + [Dev Container](https://code.visualstudio.com/docs/devcontainers/tutorial) setup is recommended for a consistent environment.

### Install

```bash
yarn
```

### Run in development

```bash
yarn dev
```

### Build

```bash
yarn build
```

## Platform Builds

### Windows

Building Windows executables on Linux / a Dev Container requires Wine:

```bash
# Add 32-bit architecture support
sudo dpkg --add-architecture i386

# Update package list
sudo apt-get update

# Install Wine
sudo apt-get install -y wine wine32 wine64

# Build for Windows
yarn build:win
```

### macOS

```bash
yarn build:mac
```

> A macOS host is required for proper code signing.

### Linux

```bash
yarn build:linux
```

Outputs an AppImage, a Snap package, and a Debian package.

## Build Output

All artifacts are written to the `dist/` directory:

```
dist/
├── browser-space-<version>-setup.exe   # Windows installer (NSIS)
├── browser-space-<version>.dmg         # macOS disk image
├── browser-space-<version>.AppImage    # Linux AppImage
├── browser-space-<version>.snap        # Linux Snap
└── browser-space_<version>_amd64.deb   # Debian package
```

## Scripts

| Command           | Description                          |
| ----------------- | ------------------------------------ |
| `yarn dev`        | Start the app in development mode    |
| `yarn build`      | Type-check and build the app         |
| `yarn lint`       | Lint and auto-fix the codebase       |
| `yarn format`     | Format the codebase with Prettier    |
| `yarn typecheck`  | Run TypeScript type checks           |

## License

Released under the [MIT License](LICENSE).
