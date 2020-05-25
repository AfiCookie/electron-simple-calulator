# electron-simple-calulator
A simple calculator made with Electron

<p align="center"><img src="./app/assets/images/SealCircle.png" width="108" height="108" alt="Obsidia-Launcher"></p>

<h1 align="center">Obsidia Launcher</h1>

<em><h5 align="center">(formerly Electron Launcher)</h5></em>

[<p align="center"><img src="https://img.shields.io/travis/Superkooka/Obsidia-Launcher.svg?style=for-the-badge" alt="travis">](https://travis-ci.org/Superkooka/Obsidia-Launcher) [<img src="https://img.shields.io/github/downloads/Superkooka/Obsidia-Launcher/total.svg?style=for-the-badge" alt="downloads">](https://github.com/Superkooka/Obsidia-Launcher/releases) <img src="https://forthebadge.com/images/badges/winter-is-coming.svg"  height="28px" alt="stark"></p>

<p align="center">Join modded servers without worrying about installing Java, Forge, or other mods. We'll handle that for you.</p>

![Screenshot 1](app/assets/images/screen1.png)
![Screenshot 2](app/assets/images/screen2.png)

## Features

* 🔒 Full account management.
  * Add multiple accounts and easily switch between them.
  * Credentials are never stored and transmitted directly to Mojang.
* 📂 Efficient asset management.
  * Receive client updates as soon as we release them.
  * Files are validated before launch. Corrupt or incorrect files will be redownloaded.
* ☕ **Automatic Java validation.**
  * If you have an incompatible version of Java installed, we'll install the right one *for you*.
  * You do not need to have Java installed to run the launcher.
* 📰 News feed natively built into the launcher.
* ⚙️ Intuitive settings management, including a Java control panel.
* Supports all of our servers.
  * Switch between server configurations with ease.
  * View the player count of the selected server.
* Automatic updates. That's right, the launcher updates itself.
*  View the status of Mojang's services.

This is not an exhaustive list. Download and install the launcher to gauge all it can do!


#### Like the project? Leave a ⭐ star on the repository!

## Downloads

You can download from [GitHub Releases](https://github.com/Superkooka/Obsidia-Launcher/releases)

#### Latest Release

[![](https://img.shields.io/github/release/Superkooka/Obsidia-Launcher.svg?style=flat-square)](https://github.com/Superkooka/Obsidia-Launcher/releases/latest)

#### Latest Pre-Release
[![](https://img.shields.io/github/release/Superkooka/Obsidia-Launcher/all.svg?style=flat-square)](https://github.com/Superkooka/Obsidia-Launcher/releases)

**Supported Platforms**

If you download from the [Releases](https://github.com/Superkooka/Obsidia-Launcher/releases) tab, select the installer for your system.

| Platform | File |
| -------- | ---- |
| Windows Setup | `helioslauncher-setup-VERSION.exe` |
| macOS | `helioslauncher-VERSION.dmg` |
| Linux x64 | `helioslauncher-VERSION-x86_64.AppImage` |

## Development

### Getting Started

**System Requirements**

* [Node.js][nodejs] v12

---

**Clone and Install Dependencies**

```console
> git clone https://github.com/Superkooka/Obsidia-Launcher.git
> cd Obsidia-Launcher
> npm install
```

---

**Launch Application**

```console
> npm start
```

---

**Build Installers**

To build for your current platform.

```console
> npm run dist
```

Build for a specific platform.

| Platform    | Command              |
| ----------- | -------------------- |
| Windows x64 | `npm run dist:win`   |
| macOS       | `npm run dist:mac`   |
| Linux x64   | `npm run dist:linux` |

Builds for macOS may not work on Windows/Linux and vice-versa.

---

### Visual Studio Code

All development of the launcher should be done using [Visual Studio Code][vscode].

Paste the following into `.vscode/launch.json`

```JSON
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Main Process",
      "type": "node",
      "request": "launch",
      "cwd": "${workspaceRoot}",
      "runtimeExecutable": "${workspaceRoot}/node_modules/.bin/electron",
      "windows": {
        "runtimeExecutable": "${workspaceRoot}/node_modules/.bin/electron.cmd"
      },
      "args": ["."],
      "console": "integratedTerminal",
      "protocol": "inspector"
    },
    {
      "name": "Debug Renderer Process",
      "type": "chrome",
      "request": "launch",
      "runtimeExecutable": "${workspaceRoot}/node_modules/.bin/electron",
      "windows": {
        "runtimeExecutable": "${workspaceRoot}/node_modules/.bin/electron.cmd"
      },
      "runtimeArgs": [
        "${workspaceRoot}/.",
        "--remote-debugging-port=9222"
      ],
      "webRoot": "${workspaceRoot}"
    }
  ]
}
```

This adds two debug configurations.

#### Debug Main Process

This allows you to debug Electron's [main process][mainprocess]. You can debug scripts in the [renderer process][rendererprocess] by opening the DevTools Window.

#### Debug Renderer Process

This allows you to debug Electron's [renderer process][rendererprocess]. This requires you to install the [Debugger for Chrome][chromedebugger] extension.

Note that you **cannot** open the DevTools window while using this debug configuration. Chromium only allows one debugger, opening another will crash the program.

---

### Note on Third-Party Usage

You may use this software in your own project so long as the following conditions are met.

* Credit is expressly given to the original authors (Daniel Scalzi).
  * Include a link to the original source on the launcher's About page.
  * Credit the authors and provide a link to the original source in any publications or download pages.
* The source code remain **public** as a fork of this repository.

We reserve the right to update these conditions at any time, please check back periodically.

---

### See you ingame.


[nodejs]: https://nodejs.org/en/ 'Node.js'
[vscode]: https://code.visualstudio.com/ 'Visual Studio Code'
[mainprocess]: https://electronjs.org/docs/tutorial/application-architecture#main-and-renderer-processes 'Main Process'
[rendererprocess]: https://electronjs.org/docs/tutorial/application-architecture#main-and-renderer-processes 'Renderer Process'
[chromedebugger]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome 'Debugger for Chrome'


[![forthebadge](https://forthebadge.com/images/badges/uses-html.svg)](https://forthebadge.com)
