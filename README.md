# Phase Study Simulator

A desktop app for testing the Phase Study ensemble without a room full of phones. It shows the conductor and a grid of simulated phones in one window. Each simulated phone joins the room like a real one, and you can send each one to its own speaker or audio channel.

The source code is in [`desktop/`](https://github.com/eamon1000000/distributed-listening-2/tree/simulator-cleanup/desktop) of the Distributed Listening repo. This repo only holds the downloads.

## Download

Get the latest version from [Releases](../../releases/latest):

- **Windows:** `Phase-Study-Simulator-<version>-win-x64.exe`. Nothing to install: just run it. Windows may warn that the app is unrecognized because it isn't signed; choose **More info → Run anyway**.
- **macOS:** `Phase-Study-Simulator-<version>-mac.dmg`. Drag the app to Applications. The first time, right-click it and choose **Open**, because it isn't signed by Apple.

## Using it

1. Serve the site and open a Cloudflare tunnel to it.
2. Paste the tunnel link into **Server link** and press **Load**. The conductor appears on the right and the simulated phones join.
   - To join a room that already exists, add `?room=ABCD` to the link.
   - Real phones can join the same room from the conductor's QR code.
3. Set the number of phones with **− / +**.
4. Use the menu on each card to choose where that phone plays: stereo on an output, or a single channel.
5. Start the piece from the conductor, or press **Space**.

On each card, **S** solos the phone (Ctrl-click, or ⌘-click on Mac, to solo several), **M** mutes it, and **♪** plays a test tone on its output. Solo and mute only change what you hear: every phone keeps playing in time.

## Building the Mac version

On a Mac, from the Distributed Listening repo:

```bash
git checkout simulator-cleanup
cd desktop
npm install
npm run dist
```

The `.dmg` is in `desktop/dist/`. Upload it to this repo's latest release.
