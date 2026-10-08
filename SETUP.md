# Impulse Studio MCP

Maintained by n3tworkspirits · n3tworkspirits@gmail.com

Make music in the Impulse Studio desktop app from any MCP client that supports local stdio servers. The app remains the instrument: you can see the notes, hear playback and undo edits manually. Each musician runs their own app and server on their own computer.

This is version 0.3.0, a local desktop integration. It has not been published to the npm registry. The browser/tablet version does not expose this connection.

## Install from a shared package

1. Install the matching Impulse Studio desktop app (a build that includes the MCP bridge), and open it. Existing older builds must be replaced with the updated app.
2. Install a supported Node.js LTS release (22 or 24), including npm.
3. Install the supplied package:

```sh
npm install -g /path/to/impulse-tracker-mcp-0.3.0.tgz
```

On Windows, use the actual path to the downloaded `.tgz` instead.

4. Add a local stdio MCP server to your client. A common JSON configuration is:

```json
{
  "mcpServers": {
    "impulse-tracker": {
      "command": "impulse-tracker-mcp",
      "args": []
    }
  }
}
```

5. In Impulse Studio, open **Assistant activity** near **Save project** and click **Resume MCP**. The status changes from **Paused** to **Ready**. Keep the app open while using your assistant.
6. Click **Pause MCP** whenever you want to block new requests. Your choice is remembered across app restarts. The music app works normally with MCP paused.

Client configuration formats differ. If the client cannot find the executable, use its full installed path, or use `node` with the full path to `server.js`. Restart/reconnect the MCP client after changing its configuration. The app must remain open. Fresh installations start with MCP paused: open Assistant activity and click Resume MCP when you want to connect. Use Pause MCP / Resume MCP in the app to suspend or resume tool access. Node and the app must run as the same OS user.

For a source checkout:

```sh
npm install --prefix mcp
npm start
```

Configure the client with `command: "node"` and `args: ["/absolute/path/to/Impulse Studio/mcp/server.js"]`. Do not use `npm run mcp` as the client command: npm's banner can interfere with stdio.

## Music workflow

Start with `get_song` and `get_pattern` to inspect existing work. Search bundled sounds, audition a sample, then assign it to a sound slot. Create named patterns with section roles, write notes in batches, and build the playback order with `set_arrangement`. Keep reusable loops with `save_loop`, create Studio sections with `create_section`, and place grouped loops with `place_loop`. Move, trim, repeat or mix whole clips using `edit_clip`. `get_drafts` and `load_loop_draft` expose saved work in progress. `search_beats` and `create_beat` provide beat presets; `import_sample` accepts a musician-supplied absolute WAV path and requires confirmation inside the app before reading it. Listen, revise, undo/redo and export. Use the `impulse` export for a complete single-file project.

Useful request: “Build a 120 BPM house sketch with separate percussion, bass and melody layers, then play it. Keep my existing patterns.”

The MCP resource `impulse-tracker://guide` describes the composition conventions.

- Pattern and row indices start at 0. Channel and sound slot numbers start at 1.
- C4 is note 48 and C5 is note 60, following the app's tracker convention.
- At speed 6 there are four rows per beat: a 16-row phrase is four beats; a 64-row pattern is four bars in 4/4. Timing effects can change this.
- Put chord tones on different channels. Each tracker channel plays one note at a time.
- Set `durationRows` to write a release for sustained notes. Omit it for one-shot drums. A release must fit inside the pattern and cannot occupy the same cell as another note in the batch.
- `write_notes` is one atomic Undo step. Failed edits roll back. Existing cells are protected unless `overwrite: true`. `clear: true` erases a cell, with the same overwrite protection.
- Use `expectedRevision` from `get_song` to reject edits if someone has changed the song since inspection. Manual edits that enter the shared Undo history also advance the revision.
- Sample-mode songs use `soundId`; instrument-mode songs use named `preset`. Switching a populated sample song to presets is rejected to preserve the meaning of existing sound slots.
- New patterns are appended; add them to the arrangement separately. Repeated pattern numbers refer to the same pattern. Duplicate a pattern before making independent variations.
- Edits autosave in the desktop app. Restart playback to hear note and channel changes. Shared effects update live.
- Stop recording in the app before composing through MCP.

## Tools

| Tool                                          | Purpose                                                                                        |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `get_song`                                    | Timing, revision, patterns, arrangement, slots and mix; channel defaults plus changed channels |
| `get_pattern`                                 | Populated note/effect cells, with a row window                                                 |
| `search_sounds`                               | Search samples and presets, with offset and limit                                              |
| `audition_sound`                              | Preview a sample without editing the song                                                      |
| `assign_sound`                                | Assign a sample or instrument preset                                                           |
| `set_song`                                    | Title, BPM and tracker speed                                                                   |
| `create_pattern`                              | Create or duplicate a named section with a role                                                |
| `write_notes`                                 | Atomic phrases, chords, releases, effects and layer groups                                     |
| `set_arrangement`                             | Playback order and repeated sections                                                           |
| `set_mix`                                     | Channel volume, pan, mute, reverb, delay and distortion                                        |
| `transport`                                   | Play song, loop pattern or stop                                                                |
| `undo`                                        | Undo the latest app/MCP edit                                                                   |
| `new_song`                                    | Replace current work with an undoable blank song                                               |
| `export_song`                                 | Full project, IT plus extra settings, S3M or WAV                                               |
| `redo`                                        | Redo an undone edit                                                                            |
| `get_loops` / `get_drafts`                    | Inspect saved loops and unfinished work                                                        |
| `search_beats` / `create_beat`                | Find and create bundled beat presets                                                           |
| `save_loop` / `rename_loop` / `remove_loop`   | Manage reusable loops                                                                          |
| `create_section` / `place_loop` / `edit_clip` | Arrange and edit Studio clips                                                                  |
| `set_musical_guide` / `load_loop_draft`       | Set the note guide or resume a loop draft                                                      |
| `import_sample`                               | Import a local WAV after confirmation in the app                                               |

Exports go to `Documents/Impulse Studio Exports`. Export names allow letters, numbers, spaces, underscores and hyphens, with no leading/trailing spaces or reserved Windows device names. Existing files are never overwritten; choose another name to save a revision. The tool returns the actual paths. WAV export uses a snapshot of the song, so further UI edits do not change the recording being rendered.

## Local connection

The app listens on a randomly allocated loopback port and writes a per-session token to `~/.impulse-tracker/mcp.json` with owner-only permissions on systems that support Unix file modes. The server discovers this file automatically. Browser-origin requests and requests without the token are rejected. The connection is local; it is not a public HTTP MCP endpoint. Do not share the connection file or token.

For separate profiles, set `IMPULSE_TRACKER_MCP_CONFIG` to the same absolute discovery-file path for both app and server. The normal app allows one instance per OS user. The stdio adapter talks only to `127.0.0.1` and refuses redirects.

Both the adapter and desktop bridge validate the same strict tool schemas; unknown tools and extra arguments are rejected. The explicit Pause MCP / Resume MCP choice persists across app restarts. Fresh installations deny tool access until Resume MCP is clicked. The bridge checks the exact loopback Host header, uses a constant-time secret comparison, accepts only uncompressed JSON and bounds request size, header size and body-reading time. The adapter refuses oversized or symlinked connection files and checks owner-only permissions on macOS/Linux. WAV imports require a regular file, a WAV header, and a maximum size of 32 MB; malformed formats are rejected. MCP WAV exports are limited to ten minutes to bound rendering memory. The adapter has no shell, arbitrary URL, general file read, or general file write tools.

The server uses the [official MCP SDK](https://ts.sdk.modelcontextprotocol.io/server) and validates tool arguments before forwarding them. Multiple requests are serialized by the app. A timeout is ambiguous: inspect the song and restart the app before retrying an edit, since it may already have applied. The app disables further dispatch after a timeout. Queued requests whose clients disconnect are discarded before execution. At most eight calls are queued, with bounded HTTP connections and request sizes.

## Development and sharing

From the project root:

```sh
npm run mcp:install
npm test
npm run test:desktop
npm run mcp:pack
npm run build:mac
npm run build:windows
npm run mcp:bundle:mac
npm run mcp:bundle:windows
```

The bundle commands create sharing ZIPs in `downloads/`, each containing the matching app, server package and this setup guide. Share a platform ZIP, or share the generated `.tgz` with the matching platform app. `npm run test:mcp:package` verifies that the packed server installs outside this checkout. The server package is standalone and includes neither songs nor recordings: the app supplies the sound library and audio engine. Source-mode desktop integration tests require the MCP dependencies installed in `mcp/`.

Verified locally on macOS: MCP handshake and tool/resource discovery, schema rejection, live composition, collision rollback, manual Undo/revision detection, playback scheduling, IT/extras and WAV export, duplicate-export protection and authentication. Windows installation, Windows MIDI/audio and use from each third-party MCP client still need verification. Audio tests verify scheduling/rendered formats, not listening quality.

## Trust and privacy

Enabling this MCP gives the connected client access to the current song, saved loops and drafts, local playback, undoable edits, and exports into the dedicated exports folder. These edits autosave. Pause MCP in the app when you do not want access. Tool annotations and `new_song` confirmation arguments guide clients; they are not a substitute for the musician authorizing a task. Undo/redo affect the app's shared history, including manual edits.

Imported audio becomes part of the song and can be included in exports. The bridge itself sends no data to an external service, but your chosen MCP client may send tool results or exported content to its model provider according to that client's settings. Local processes running as your OS user can read the session token; this is not a security boundary against malicious software already running under your account. On Windows, the app applies and checks a protected owner-only ACL before writing any token. This uses the installed Windows PowerShell and does not accept executable input from MCP tools. If ACL protection fails, the MCP connection remains unavailable while music editing stays usable. Administrators and processes running as your user remain outside this boundary. Native ACL execution, installation and audio still require Windows verification.

## Windows specifics

Use a current-user installation and run the app and MCP client as the same regular Windows user. The installer does not offer automatic elevation; the application needs no administrator rights for music or MCP. Builds are unsigned and may produce Windows publisher/SmartScreen warnings.

WAV import and custom discovery paths must use ordinary drive-absolute paths such as `C:\Music\sample.wav`. UNC shares, device namespaces, alternate data streams, reserved names and trailing dots/spaces are rejected before resolving a path. Keep a custom discovery file in a private user directory, not a shared or synchronized location.

Global npm installs create a Windows command shim. Some MCP clients cannot start that shim directly. Use `node.exe` as the command with the absolute installed `server.js` as its sole argument; `npm root -g` identifies its `node_modules` parent. In JSON, double each backslash in a Windows path, or use forward slashes. Paths containing spaces belong in one argument and need no embedded quotes. Restart the client after changing PATH or installing Node.

For native verification from a source checkout, run `npm run test:mcp:windows` on Windows to exercise real ACL creation, then test the installer, MCP handshake, pause/restart, denied/approved WAV imports, duplicate exports, and uninstall/reinstall retaining saved songs. The Windows-specific policy and fail-closed publication tests can run on other platforms, but they explicitly skip native ACL execution there.

## DJ workflow (0.3.0)

Read `impulse-tracker://dj-guide`, then call `get_dj`. Nine DJ tools are available: `get_dj`, `dj_load`, `dj_transport`, `dj_mix`, `dj_sync`, `dj_loop`, `dj_pad`, `dj_record` and `dj_set`. See [DJ_GUIDE.md](DJ_GUIDE.md) for arguments, workflow and limits. They inspect and control the same DJ mode visible in the app, including saved library audio and Studio sources. DJ controls act live outside Studio Undo/song revisions. The existing 28 composition tools keep their behavior.

Example: “Inspect my DJ decks and Studio loops. Load this Studio section into deck A, set its volume to 60%, and leave it paused.” Recording export, device routing, file import and library/cue editing remain in the app. The adapter returns metadata rather than audio bytes. A client can now read local DJ track/set names and control playback, recording and saved sets when MCP is enabled.

Update an installed adapter with `npm install -g /path/to/impulse-tracker-mcp-0.3.0.tgz`, then reconnect the client so it discovers the new tools. Source-based configurations use the updated server directly after reconnecting. Use the matching updated desktop build.
