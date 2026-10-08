# Impulse Studio 0.1.1 — First public release

Welcome to the first public release of **Impulse Studio**: a retro, cosy music-making app for macOS and Windows.

Impulse Studio began with inspiration from [Impulse Tracker by Jeffrey Lim](https://github.com/jthlim/impulse-tracker) and grew into a broader music-making app, with pads, keyboards, visual song arrangement and DJ mixing, while keeping its retro roots.

Made by **n3tworkspirits**.

## Make music

- Write patterns in the classic tracker.
- Play and record with 36 pads, an on-screen keyboard and Drum Studio.
- Layer sounds and arrange sections in the visual Studio workspace.
- Explore bundled instruments, drums, vocals, loops and textures.
- Edit samples, add effects and save reusable parts.
- Save projects and export your music.

Bundled sounds work offline in the desktop app.

## DJ mode

Mix local tracks or bring your Studio music onto two decks. Use the crossfader, EQ, filter, echo, tempo controls, cues and loops, then add your own sections through four performance pads.

Organise tracks into playlists, preview through headphones, save sets, and **record and export your DJ mixes as lossless WAV**.

## Optional MCP connection

Connect a compatible assistant to the running desktop app to help build music or control supported DJ features. The included MCP 0.3.0 adapter offers 37 tools, with setup instructions and guides.

MCP starts paused on fresh installations. Follow `SETUP.md`, open **Assistant activity** near **Save project**, then click **Resume MCP**. **Ready** means the app accepts requests. Keep the app open; click **Pause MCP** to block new requests. Your choice is remembered.

MCP is optional. You don’t need it or Node.js to use the music app. Only connect clients you trust; their privacy settings apply to the data they receive. Studio edits support Undo; DJ actions operate live outside Studio Undo.

## Downloads

| Package | Platform |
| --- | --- |
| `Impulse-Studio-MCP-Mac-arm64.zip` | Apple Silicon Mac |
| `Impulse-Studio-MCP-Windows-x64.zip` | Windows x64 |
| `Impulse-Tracker-Tablet.zip` | Tablet browser edition |
| `impulse-tracker-mcp-0.3.0.tgz` | Optional standalone MCP adapter |

The desktop bundles include the app, optional MCP adapter and setup instructions. Matching `.sha256` files are supplied to verify downloads.

On Mac, unzip the package and move **Impulse Studio.app** into Applications. On Windows, unzip the package and run the installer.

The tablet edition requires a web server; it is not an iPad or Android installer. Follow its `START-HERE.txt` instructions and serve only the extracted app folder on a trusted local network.

## Early-release notes

These builds are unsigned, so your operating system may display a security prompt. Intel Mac and native Windows ARM builds are not included.

Desktop, DJ and MCP automated checks have passed. The Windows package was built on macOS and still needs native Windows installation, audio, MIDI and permissions testing.

DJ beat sync depends on the track’s beat grid; variable-tempo music may drift. DJ mixes are recorded as 32-bit float stereo WAV, using about 23 MB per minute at 48 kHz. Lossless recording preserves the mix without adding compression; it cannot restore detail missing from compressed source tracks.

## Future updates

New downloads and release notes will appear here. Subscribe through the repository’s **Watch** menu, or use **Check for updates** in the desktop app to check the public release feed. Checks run when requested and contact GitHub; installation is manual.

## Feedback and credits

Report problems through [GitHub Issues](https://github.com/n3tworkspirits/impulse-studio/issues) or **n3tworkspirits@gmail.com**.

Made by **n3tworkspirits**. Impulse Studio draws on the original Impulse Tracker source under its BSD 3-Clause licence. Credits and licences for third-party code and bundled sounds are included with the app.
