# GorillaNet

A simple custom web browser for Windows, built with [Electron](https://www.electronjs.org/) (which uses the Chromium engine, the same one behind Chrome and Edge).

## Features

- Address bar that accepts web addresses or search terms
- Back, forward, and reload buttons
- Searches with Google when you type something that isn't a web address
- Runs on a real Chromium engine, so modern websites work

## Requirements

- Windows 10 or 11 (64-bit)
- [Node.js](https://nodejs.org/) (LTS version)

## Run it (for development)

1. Open a terminal in the project folder.
2. Install the dependencies:
   ```
   npm install
   ```
3. Start the browser:
   ```
   npm start
   ```

## Build the .exe

1. Install the packaging tool (only needed once):
   ```
   npm install @electron/packager --save-dev
   ```
2. Build the app:
   ```
   npx @electron/packager . GorillaNet --platform=win32 --arch=x64 --overwrite
   ```
3. When it finishes, open the new **`GorillaNet-win32-x64`** folder and run **`GorillaNet.exe`**.

> `win32` is just Electron's name for Windows. `--arch=x64` is what makes it 64-bit.

The build can take a few minutes and may look stuck while it downloads Electron. Wait until you see a line starting with `Wrote new app to`.

## Sharing the app

The `.exe` needs the other files in its folder to work. Zip the whole `GorillaNet-win32-x64` folder (right-click > **Send to > Compressed (zipped) folder**) and share the zip. People unzip it and run `GorillaNet.exe`.

Windows may show a blue **"Windows protected your PC"** warning because the app isn't digitally signed. Click **More info > Run anyway**.

## Project files

| File | What it does |
| --- | --- |
| `main.js` | Creates the desktop window |
| `index.html` | The browser's interface: toolbar, buttons, and the area where websites appear |
| `package.json` | Project name, version, and start command |

## Troubleshooting

- **Packaging stops with no error:** pause your antivirus for a moment, make sure the folder isn't inside OneDrive, or run the terminal as Administrator.
- **Can't find the .exe:** make sure you ran the build command from inside the project folder, then look for the `GorillaNet-win32-x64` folder.

## Roadmap

- [ ] Tabs
- [ ] Bookmarks
- [ ] History
- [ ] Custom icon
- [ ] Dark mode
- [ ] Installer (Setup.exe)

## Disclaimer

GorillaNet is an independent project and is not affiliated with or endorsed by Another Axiom or the game Gorilla Tag.
