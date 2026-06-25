# Session Forge Browser

> A multi-account browser session manager — run isolated Gmail, Slack, and web accounts side by side in named workspaces.

Session Forge Browser lets you stay signed in to multiple accounts on the same site at the same time. Each profile runs in a fully isolated browser session — separate cookies, storage, and cache — so your work, personal, and client accounts never collide.

## Features

- **Isolated sessions** — every profile has completely separate cookies, localStorage, cache, and session data
- **Customizable profiles** — name each profile, pick from 400+ icons or upload a custom image, and choose a color
- **Per-profile language** — set the browser language individually for each profile (15 languages)
- **Notification control** — configure notifications per profile (Allow all / Ask / Block all), with the source profile shown in every alert
- **Collapsible sidebar** — switch between icon-only and icon + name views
- **Drag & drop ordering** — organize profiles the way you work
- **Data management** — clear cookies, cache, and app data per profile
- **Crash recovery** — unresponsive or crashed sessions can be reloaded without restarting the app
- **Lightweight** — built on Electron and tuned for fast switching

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
