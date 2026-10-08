# Impulse Studio

A retro, cosy music-making app for macOS and Windows.

Impulse Studio began with inspiration from [Impulse Tracker](https://github.com/jthlim/impulse-tracker) and grew into a broader music-making app, with pads, keyboards, visual song arrangement and DJ mixing, while keeping its retro roots.

Build beats, play melodies and turn small ideas into songs. Work with the classic tracker, use pads and a keyboard to record parts, or put everything together in the visual arranger. Switch to DJ mode to mix tracks with two decks, loops and performance pads.

Made by **n3tworkspirits**.

## Make music

- Write patterns in the tracker or play parts with 36 pads and an on-screen keyboard.
- Build drum patterns, record melodies and save reusable loops.
- Layer sounds, arrange sections and adjust your song as it plays.
- Explore bundled instruments, drums, vocals, loops and textures.
- Shape samples with effects and editing tools.
- Save projects, reopen tracker modules and export your music.

Bundled sounds are included with the desktop app and work offline.

## DJ mode

Mix local tracks or bring your Studio music onto two decks. Use the crossfader, EQ, filter, echo, tempo controls, cues and loops, then add your own sections through four performance pads.

Organise tracks into playlists, preview through headphones, save sets, and **record and export your DJ mixes as lossless WAV**.

## Download

Get the [latest release](https://github.com/n3tworkspirits/impulse-studio/releases/latest).

| Download | What it includes |
| --- | --- |
| [Mac Apple Silicon](https://github.com/n3tworkspirits/impulse-studio/releases/latest/download/Impulse-Studio-MCP-Mac-arm64.zip) | Mac app, optional MCP package and setup instructions |
| [Windows x64](https://github.com/n3tworkspirits/impulse-studio/releases/latest/download/Impulse-Studio-MCP-Windows-x64.zip) | Windows installer, optional MCP package and setup instructions |
| [Tablet browser edition](https://github.com/n3tworkspirits/impulse-studio/releases/latest/download/Impulse-Tracker-Tablet.zip) | Browser package for serving through a local web server |

The release also includes the standalone MCP package and `.sha256` files for verifying downloads.

You can use the desktop app without installing MCP or Node.js.

For Mac, unzip the download and move **Impulse Studio.app** into Applications. For Windows, unzip the download and run the included installer.

These early builds are unsigned, so macOS or Windows may display a security prompt. The Mac build supports Apple Silicon; an Intel Mac build is not included. The Windows build targets x64 and still needs native installation, audio, MIDI and permissions testing on Windows.

The tablet download is a browser package, not an iPad or Android installer. Follow its `START-HERE.txt` instructions. Serve only the extracted app folder on a trusted local network. Songs stay in the tablet browser; export projects to move them between devices.

## Optional MCP connection

MCP lets a compatible assistant work with the music app running on your computer. It can inspect your song, help build patterns and arrangements, and control supported DJ features.

Follow [SETUP.md](SETUP.md) to install the optional package and configure your client. Then open **Assistant activity** near **Save project** and click **Resume MCP**. The status changes from **Paused** to **Ready**. Keep Impulse Studio open while using it.

Fresh installations start paused. **Pause MCP** blocks new requests, and the app remembers your choice. Studio edits support Undo; DJ playback and mixing controls act live outside Studio Undo.

Connect only clients you trust. A connected assistant can receive song data, track names and export paths; its provider’s privacy settings apply. The app stores music locally and has no automatic cloud sync or sharing between separate computers.

## Updates

New versions and release notes appear in [Releases](https://github.com/n3tworkspirits/impulse-studio/releases). Use GitHub’s **Watch** menu to subscribe to releases.

In the desktop app, use **Check for updates** from Home or the Help menu to check the public release feed. Checks run when requested and contact GitHub. Updates are installed manually: download the new package and replace the Mac app or run the new Windows installer. Export a copy of important projects before updating.

If you use MCP, follow the release notes to update the adapter too. Updating the desktop app does not update a separately installed MCP package.

## Help and feedback

Use the Help buttons in the app or read the [user guide](docs/USER_GUIDE.md). The optional integration has a [setup guide](SETUP.md) and [DJ workflow guide](DJ_GUIDE.md).

Found a problem or have an idea? [Open an issue](https://github.com/n3tworkspirits/impulse-studio/issues) or email **n3tworkspirits@gmail.com**.

For bug reports, include your app version, operating system, what you were doing and what happened. Screenshots or a small example project can help reproduce the problem. Remove personal information before posting files publicly.

## Credits

Impulse Studio draws on [Impulse Tracker](https://github.com/jthlim/impulse-tracker), created by Jeffrey Lim. Its palettes, custom glyphs, screen layout and keyboard table derive from the original source, used under its BSD 3-Clause licence.

Bundled sounds come from several creators and libraries, with their own licences. See [NOTICE](NOTICE) and the [sound library documentation](docs/SOUND_LIBRARIES.md). Credits and licence information are included with the app; sample attribution is also available in Sample Playground.

This repository hosts downloads, release notes and supporting documentation. The Impulse Studio development repository is private while I work on it.

**n3tworkspirits** · **n3tworkspirits@gmail.com**
