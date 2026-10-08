# Impulse Studio user guide

## Your first tune

A tracker plays music from a grid. Time runs down the screen one row at a time, and each column across is a channel that plays one sound at once.

1. **Hear the demo.** `F5` plays it, `F8` stops.
2. **Choose a sound.** `F3` opens the Sample List. With the cursor on "Play", the letter keys play the selected sound. `Ctrl+F3` opens the built-in sounds; `Enter` adds one.
3. **Compose a part.** Open **Pads**, **Keyboard**, or **Drum Studio**. Assign a sound, preview it, then record a performance or enter steps.
4. **Add layers.** In **Song arrangement**, browse samples and drum patterns, then add them to a section.
5. **Hear your music.** Use **Play song** or **Loop section** in the arranger.
6. **Build a song.** Add, duplicate and reorder sections in **Song arrangement**.
7. **Keep your work.** It saves in the browser as you go. `F10` saves an `.IT` file, `F9` loads one, and "Export .wav" makes a recording.

`F1` inside the program shows this guide followed by every key.

## Write a track with pads

Open **Pads** for a controller panel with 36 coloured pads, pitch/level/step/tempo controls and a part display. Right-click a pad to select it without playing. Tap a pad in **Listen** to hear it, then use **Assign** on that tile to open a searchable chooser and choose a built-in sound or one already in your song. Set its pitch, level, role and tracker channel. **Chord** plays three notes; **Keys** spreads the selected sound across 36 pitches for playing a tune.

Choose **Write** to enter each hit at the current tracker row and advance by **Step**. Click the selected pad's step grid to add or remove hits. Choose **Record**, press **Play**, and tap a performance: notes land in the pattern being heard, snapped to the selected step size. **Song arrangement** shows the recorded sections. Undo restores edits. **New part** adds a blank pattern; **Song arrangement** organises and duplicates your sections.

Turn knobs by dragging up/right or scrolling; hold Shift during dragging for finer changes. Arrow keys adjust a focused knob, and the number fields accept exact values. **Reverb** beside the pad settings controls the shared room effect for all pads and song playback (0 is off, 128 is maximum; 64 keeps its previous strength). It updates during playback and is included in saved extra settings.

One drag is one Undo step. Pad shortcuts also work while a slider has focus; an active drag keeps adjusting its original pad while you play other tiles.

Keyboard pads: **Q W E / A S D / Z X C / V B N** for tiles 1–12; **R T Y U I O P F G H J K** for tiles 13–24. Every tile displays its unique key. **Tab** selects a pad without playing; arrows move the row; **Space** plays/stops. **Alt+L/W/R** selects Listen/Write/Record, **Alt+K** toggles Keys, and **Alt+A** assigns a sound. Delete clears the selected pad's notes at the current row. Assignments survive autosave, song copies, links and the companion extras file.

## Sound collections

The sound library now includes **232 core CC0 recordings**, additional licensed loops and playable synthetic sounds. See the [sound library documentation](SOUND_LIBRARIES.md) for sources and attribution. In Pads, click **Assign** on a tile and choose a **Collection**; search filters within that collection, and the play button previews a sound before assigning it. The library is also available from Sounds / Ctrl+F3.

Recordings are mixed into the existing collections:

- **House & techno:** 44 dance drum/FX samples, sweep pad, fifths lead, saxophones and siren whistle.
- **Orchestral:** recorded strings, woodwinds, brass and mallets.
- **Dungeon synth:** recorded organs, harp, harpsichord, tubular bell and gong.
- **Classic:** grand/upright piano and Yamaha TX81Z keys.
- **Metal:** recorded guitars, bass, acoustic drums and four metal growls.
- **Vocals & opera:** live children’s choir phrases, five male sung vowels, five crowd vowels, five female sung notes and four vocal chops. The female voice preset uses the closest of its five recordings across the keyboard.
- **Psytrance:** sampled basses, bass lead and sci-fi texture.
- **World percussion:** recorded kalimba.

New collections add **Keys & mallets**, **Acoustic instruments**, **Acoustic percussion**, **Vocal shouts & chops**, and **Vocal phrases & textures**: 47 additional recordings covering Steinway piano, soft mallets, lute harpsichord, recorders, tom/triangle rolls, vocal shouts, growl chops, humming and sung phrases. In Song arrangement, use **Collection** and **Find a sound** to browse them, preview, then add or drag a sample into a section. Sung vowels default to their natural register; previews leave the song unchanged. The drum pattern library includes seven editable beats that follow the song tempo.

Recordings ship locally with the desktop app and website, so playback works offline. Preview plays them at the reference note; live choir previews run long enough to hear the performance. Assigning a recorded drum, choir phrase or vocal effect uses original/reference speed and single-note mode. The Instruments library includes recorded instrument presets, a metal drum kit, a live choir phrase kit and a metal vocal kit.

The full source selection, coverage gaps, licences and rebuild instructions are in [sound library documentation](SOUND_LIBRARIES.md). The bank contains a curated selection, rather than entire multisampled libraries. Source licences ship in `src/recordings/licenses`; exact sources and checksums are retained in the recording manifest. Existing song samples and sound IDs are preserved. Unedited recorded built-ins support pad recording, reusable sequences, effects, saved modules and song links.

## Reusable sequences

In Pads, enter a **Sequence name**, then choose **Record sequence**. It adds a fresh looping part; tap pads to capture notes on the heard row, snapped to Step. **Stop & save** stores that performance in the song's sequence library. You can also use **Save sequence** on a part you've already written.

Choose a name under **Saved sequences** and press **Add part** to insert an independent copy into the order list. Reuse it as often as you like, then arrange it in Song arrangement. Saved sequences retain notes, levels, effects and sound assignments; editing a copy leaves the saved sequence unchanged. The library stays with this song through autosave, song copies, links and the companion extras file. Undo covers saving and adding parts.

## Arranging and making a song

The strip above the pattern grid shows the order list. Click a block to jump, drag it to reorder, and use the arrows at its edges to reach later orders. A marker follows playback.

- **Duplicate section** in Song arrangement copies a section and inserts it after the selected section.
- **Shift+arrows** marks cells. **Alt+D** expands the marking from a beat to a bar to the whole pattern.
- **Alt+N** names a pattern; **Alt+K** cycles the current channel's colour.
- **Alt+R** repeats a marked block down the pattern. **Alt+F** copies its first row every other row. **Alt+X** fills the selection with random notes in the chosen scale. Without a selection, the latter two fill from the cursor to the end, in the current channel.
- Notes outside the song's saved scale dim. **Shift+note** writes a three-note chord across neighbouring channels.
- **Starter songs** offers dungeon synth, chiptune, techno and metal sketches. Choosing one replaces the current song; Undo restores it.

**Record notes** puts typed notes on the row currently being heard. The pattern editor has channel activity meters, and the Info page has a scope. **Metronome** clicks on highlighted beats. Its adjacent **Settings** button controls independent volume, beep/woodblock/soft sounds, first-beat accent, recording-only clicks and an off/one-bar/two-bar recording count-in. Settings persist on this device; count-in follows the song’s beat and bar highlights. With Record notes enabled, Play song or Play pattern starts the count-in. Tap **Tap tempo** several times at the pace you want. Ctrl+Z, Cmd+Z or **Undo** restores changes across all screens, including samples, settings and order edits. Undo keeps the last 30 changes in the current session.

**Keep song** saves a named copy in this browser; **My songs** opens one. Autosave includes pattern names, channel colours and the scale. **Save .IT** downloads the module and a companion `.extras.json` file. Allow both downloads and keep them together (use **Save extra settings** if the browser blocks the second download); load the module first, then its companion through **Load** to restore the extra settings and reverb.

**Copy song link** carries notes, instruments and settings, recreating unedited built-in sounds on opening. Imported or edited recordings require an `.IT` file. The tracker must be available at the link's address for the recipient; a `localhost` address works only on the machine running the server.

Cherry Blossom has drifting petals, Dungeon Synth has rain and Pixel Owl blinks. Animation pauses when the system requests reduced motion.

## Checking changes

Run `node tests/features.js` for the editing and song-model checks. Open `/tests/` on the local server for the full browser checks, including IndexedDB, compressed links and canvas rendering. Browser checks create and remove their own temporary saved-song entry.

## Instruments

Samples are plain recordings. Instruments (`F4`) add behaviour on top: swelling in, fading out, ringing on under the next note, or putting a different drum on each key. Select a slot on the Instrument List and press `Enter` to choose a ready-made one. Adding an instrument switches the song to instrument mode.

## Looks and extras

- **Skin**, on the left, cycles through the colour schemes.
- **Reverb** is the last slider on the Song screen (`F12`). The companion extras file remembers it; the `.IT` format cannot store it.
- **Mouse:** click to move the cursor or press a button, drag to mark cells or move a slider, and click a channel's name to mute it.

## Files it understands

It loads `.IT`, `.XM`, `.S3M`, `.MOD` and `.MTM` modules and `.wav` samples, and saves `.IT`, `.S3M` and `.wav`.

## Credits

Layout, colours, characters and keys come from the original source code, used under its BSD 3-Clause licence. See [NOTICE](../NOTICE).

Pad **28** starts with a low Double bass. Extra keys for pads 25–36 are **L M 1 2 3 4 5 6 7 8 9 0**. Existing 12- and 24-pad assignments are preserved.

**Delay** adds quarter-note echoes in time with the tempo (0–64). Reverb and delay apply to pads and song playback, including audio export. Name your pad bank and click **Save setup**, then select it and **Load setup**. **Export setup / Import setup** transfers a JSON bank including custom samples, assignments, levels, pitches, channels, step size and effects. Setups are saved with song extras; loading preserves patterns and sequences. Custom instruments require the same song instrument mode. Up to 32 setups can be kept per song.

## MicroFreak and KO II MIDI

Open **Hardware · MicroFreak / KO II** at the bottom left and click **Connect MIDI**. Connect both devices to the computer by USB. Choose each device's input and output ports, and match its MIDI channel to the hardware settings. The defaults are channel 1 / tracker track 1 for MicroFreak and channel 2 / tracker track 2 for KO II; change these if your hardware uses other channels.

Incoming notes audition the currently selected tracker sound. Enable **Record** to write notes and velocity into the chosen tracker track. While stopped, notes advance by the Pads Step setting; while playing, they record into the audible pattern, quantized to that setting. Recording participates in undo and autosave. Each route is monophonic: use it for one melody or one drum voice, and make further passes for other parts. Releases in the same quantized row are skipped to preserve the note. A hardware pad's transmitted MIDI note is kept as its pitch; automatic KO II bank/pad mapping is not included.

Enable **Send notes** to play that tracker track on the selected hardware output. Notes end when replaced, when a note-off/cut/fade marker occurs, or when playback stops. Tracker effects such as pitch slides and arpeggios are not converted into hardware automation. Internal tracker sounds still play. **Send clock** sends MIDI clock plus Play/Stop; configure the hardware to receive external MIDI clock. The tracker is the clock source; receiving hardware transport/clock is not implemented. Routing changes clear queued hardware messages; stop and restart playback after changing routes. **Stop all hardware notes** stops the tracker and clears hardware notes. Port choices and routing switches are session settings and must be selected again after reopening.

MIDI carries performance data. MicroFreak audio capture requires an audio interface and is not implemented in the tracker. Existing sample WAV exports can be loaded into the KO II through Teenage Engineering's EP Sample Tool. Use the desktop app or a browser supporting Web MIDI, such as Chrome on localhost. Physical hardware timing and sound need verification with the devices attached.

**Reset instrument:** on Pads or Keyboard, restore the selected sound’s reference pitch and original level. On Instruments (F4), click Reset instrument or press Alt+R to restore its original settings, envelopes and note mapping. Reset supports Undo. Instrument originals are saved in autosave and companion extra settings files.

On **Keyboard**, turn **Chords on** to play and record three-note chords in the selected key and scale. Turn it off for single-note melodies. Chord mode is saved with the song; the keyboard uses three adjacent tracker channels.

**Drum kits:** on Pads, choose a Drum kit and click Load drum kit to fill pads 1–12. House, Deep house, Techno, Garage, Electro, Psytrance, Latin, World, Acoustic metal and Dance percussion & FX kits are also available in the Instruments library. Other pads and existing notes are retained; loading a kit supports Undo.

In Pads, **Record sequence** starts a fresh section after four audible count-in beats at the current tempo. Tap sounds over the repeating section; pads sharing a track are placed on separate recording tracks. **Stop recording** keeps your take. **Add layer** records into the same section after another count-in. **Clear selected layer** removes the selected pad’s track; **Clear section** empties the section. Both clear actions can be undone. Name your section and choose **Save sequence** to keep a reusable copy.

**Song arrangement** opens a full-window timeline. Select a section, rename it, move it with the buttons or drag its header, duplicate it, or remove it from the song. Add samples as separate layers with a start row, optional repeat interval, pitch and level. Saved sequences can be layered into the selected section. Select a layer block to clear it. **Record with Pads** opens that section for a counted-in recording pass. Repeated sections become independent when edited here. Arrangement edits autosave, support Undo, and use the same song data for playback and export.

In Keyboard, **Record with song** uses the count-in selected in Metronome settings and plays the whole arrangement from the beginning while you record your melody. Notes follow the section being heard and use a separate free layer. Repeated sections become independent for the performance. **Stop** keeps your melody directly in Song arrangement; no import is needed. **Record melody** remains available for a separate reusable sequence.

Playback controls are explicit: **Play song** and **Play section** play the backing and let you practise without writing notes. **Preview instrument** stops playback and auditions the chosen sound. **Record with song**, **Record new melody**, and **Record into section** start recording after the count-in selected in Metronome settings. The display shows whether notes are being recorded. Space starts practice playback when stopped. Keyboard hides the old Listen/Write/Record mode switches.

Keyboard notes follow how long you hold the typing key or on-screen piano key. Releasing one key releases its own note; recording writes a note-off at release instead of ending after a fixed step. Leaving Keyboard or switching away from the app releases held notes.

In Keyboard, **Record new melody** becomes **Stop recording** during the count-in and recording. Click the same button to stop; it immediately becomes **Record new melody** again. Starting another take keeps earlier takes as sections in Song arrangement. **Save melody** saves the most recently stopped take as a reusable sequence; saving is optional before starting another take.

Keyboard has **Hold notes**: on latches a note after key release; tap the same pitch again to stop it, or another pitch to replace it. Turning Hold notes off, Stop, or leaving the screen releases held notes. **Octave − / +** (Shift + Down / Up) shift the piano and typing-key pitches together; the current note range is shown beside the buttons.

Song arrangement separates **song roles** (Intro, Verse, Pre-chorus, Chorus, Bridge, Breakdown, Outro, Custom) from **layer groups** (Percussion, Melody, Vocals). Choose a role and name, then Save section name or New section. Each section has drop areas for the three layer groups. Drag a saved sequence or selected sample into a drop area to add it; dragging a timeline layer to another section copies it. Drag within the same section to reclassify a layer. Sequence group selectors organise the library, and Layer sequence is available without dragging. Names, roles and groups autosave and are included in extra settings.

Arrangement layer groups now include **Percussion, Bass, Melody, Vocals and Effects**. Bass sounds and transition/effect sounds are recognised automatically; group selectors let you change the classification. All five groups support the same drag-and-drop layering and saved-part organisation.

The Keyboard playback toggle now switches between **Play full sound** (tap and let the complete sound play once) and **Hold to play** (release the key to release the note). Full sound does not latch or toggle a pitch off on a second tap; tapping again retriggers it. Stop ends playback.

## Studio and reusable parts

Song arrangement opens as the main Studio. Use its Pads, Keyboard and Drum Studio navigation to make loops. New pad/keyboard recordings and New loop drafts stay outside song orders. Save to My parts keeps a reusable copy in the current project. Add to Studio lets you layer that copy into an existing section or create a new section of the part's length. Existing placements are independent copies. Record into section and Record with song remain explicit ways to record directly into the arrangement.

The Studio library opens on My parts, with separate Preset beats and Samples tabs. Song name, tempo, My songs, Load, save and audio export are available in the Studio.

The Studio shows section duration in bars and rows, with bar dividers and section widths proportional to duration. Set length extends a section with empty rows and refuses to shorten across notes. Repeat layer copies the opening loop across that placement. Layer names, volume, mute and solo apply to a section independently and persist in companion settings; WAV export uses that mix. Other trackers do not read these added placement mix settings; use WAV export to share the exact mix.

Edit in Keyboard uses step entry into the selected placement. Edit in Drums edits the selected layer in 16-step pages, saving when changing pages or returning to Studio. Other layers and saved library parts remain independent. Master effects are in the Studio and affect the whole song.

## DJ mode

Open **DJ mode** in the sidebar (on small screens, use the creation menu). Each deck plays independently. **Load track** imports local audio; you can also drop a file onto either deck. Open **Load from Studio** on a deck, then choose the full current song, a section, or a saved loop and click **Load from Studio**. Studio sources are rendered as independent audio copies with their starting BPM when tempo is constant. Reload a source after editing it in Studio. An unsaved creator performance must first be kept as a loop or added to Studio.

Press Play on each deck and use the crossfader to blend A and B. Each deck has volume, low/mid/high EQ, position, speed and 50 ms nudge controls. For imported tracks, enter the original BPM or tap along; **Match tempo** matches the other deck's current tempo. Match tempo changes speed only; Sync beats also aligns the beat grids. Pitch lock preserves pitch by default. Set a cue at the current position and press it again to jump back; the adjacent clear button removes it. **Loop in** and **Loop out** define a repeating region; **Exit loop** continues playback. Stop resets the deck to the start and exits its loop.

Decks stop when leaving DJ mode. Imported audio, corrected beat grids and cue points are saved separately in the on-device DJ library; they are not stored in Studio project files. Open Track library & playlists to load them again after restarting. Mixer settings and deck assignments can be saved under Saved DJ sets. External DJ-controller mappings are not included. The main Export audio action exports the Studio song, not the DJ performance.

### Record and cue a DJ mix

**Record mix** captures the stereo audience mix after EQ, deck volume, crossfader and master processing. **Finish recording** keeps it in a separate on-device recording library. Leaving DJ mode, using Stop all audio, or closing the desktop app finishes and stores the take. Choose a recording and **Save recording** to export WAV or its original audio file. New recordings capture lossless 32-bit float stereo WAV at the audio context sample rate, using about 23 MB per minute at 48 kHz. Export preserves those original samples. Recordings finish automatically at two hours or the WAV size limit. Older compressed recordings remain supported; converting them to WAV cannot restore lost detail. For those older recordings, WAV conversion is available up to 30 minutes; longer takes use Original audio. Recordings remain on this device across app launches; export files for backups.

Under **Audio routing & headphones**, click **Find outputs**. For **Separate headphone device**, choose two different named audio outputs and **Apply routing**. For a DJ splitter cable, choose **DJ splitter: master left / cue right** and Apply routing. This sends mono audience audio on the left channel and mono headphone audio on the right; ordinary Y-cables do not separate the signals. Press **Headphones** on a playing deck to preview it before its volume fader and crossfader, then use headphone volume and the cue/master blend. This preview never enters the recording, which stays stereo even in splitter mode. Separate-device latency depends on the hardware; wired outputs are preferable for beatmatching. If devices change, headphone cueing turns off until routing is applied again.

**Remove track** clears a deck, including its cues and loop, and cancels any pending load. It leaves the other deck and any active recording running. Source files and Studio music are unchanged.

### Beat sync, pitch lock and playlists

Loading a track analyses up to its first two minutes for a steady BPM and beat grid. The result is an estimate: sparse music, tempo changes and half-time rhythms may need correction. Edit Original BPM, use ½ BPM or 2× BPM, and pause/seek to a beat then press **Beat here** to set the grid origin. Silence or unreliable detection leaves BPM for you to enter or tap. Studio sources retain their known constant BPM.

Press **Sync beats** on the following deck to match the other deck's current tempo and beat phase. It follows subsequent tempo changes while active; the other deck becomes the leader. Starting a synced deck realigns it. Manual speed changes, seeking, nudging, cue jumps or setting a loop turn sync off on that deck. Press Sync again to release it. This uses a constant beat grid, so variable-tempo recordings can drift and require manual corrections.

**Pitch lock** is on by default. It uses stereo-linked time stretching to preserve pitch between 0.5× and 2× speed; large tempo changes can soften transients or introduce texture. Switch it off for the traditional effect where pitch rises or falls with speed. Both paths feed the same EQ, cue and recording buses.

**Track library & playlists** retains imported audio on this device, identified by its contents so reimporting the same file recalls its cues and grid. Create a named playlist, use Add deck A/B, select a track and Load into A/B. Move up/down changes playlist order. Remove from playlist removes membership only; Remove track clears a deck only. Neither deletes original source files. Cue and BPM corrections save automatically. Keep original audio backed up; this local library is separate from portable Studio project files.

### Beat loops, effects and Studio performance pads

The **Beat loop** buttons create 1, 2, 4, 8 or 16 beat loops using the deck’s original BPM and beat grid. **½ loop** and **2× loop** resize an active loop while retaining playback position within it. Correct the grid first if needed. Loops must fit inside the track; **Exit loop** returns to normal playback.

Open **EQ & effects** on either deck. The filter cuts high frequencies to the left and low frequencies to the right; the centre is neutral. Echo offers quarter-, half- and one-beat repeats at the deck’s current tempo, falling back to 120 BPM when unknown. **Echo out** fades the track into a decaying echo and pauses it; press Play to return. **Reset effects** restores the filter and removes echo. Effects feed both the deck headphone preview and the recorded main mix.

Open **Studio performance pads**, select a saved loop or Studio section and load one of four pads. Choose which deck to follow; tap a pad to queue it on that deck’s next beat and tap again to stop or cancel it. **Loop** repeats the rendered audio; turn it off for one-shot playback. Pads follow a playing deck’s tempo when the Studio source has a constant BPM; their pitch changes with speed. Without a playing deck they start immediately at their original tempo. Variable-tempo sources keep their original tempo. Pad volume is independent of the crossfader, and pads are included in mix recordings. Save a DJ set to keep assignments across sessions. Reload after changing the source in Studio. **Stop pads** stops just the pads; **Stop all audio** stops decks and pads and finishes recording.

### Finding tracks and saving DJ sets

Search the library by track name, mark favourites, filter to favourites and sort by name or BPM. Tracks with unknown BPM appear last. Choose Playlist order and clear search/favourite filters to use Move up/down. **Remove saved track** hides the library copy and its playlist entries; **Undo last removal** restores the most recently removed copy, even after restarting. Repeat undo for earlier removals. This does not reclaim audio storage or delete source files, deck audio or saved sets. Reimporting the same audio also restores it.

Select a library track and press **Headphone preview** to audition it without loading a deck. Configure separate headphones or a DJ splitter first. Headphone volume and Cue / master blend apply; move the blend toward Cue to hear the preview. Stop preview, changing the library selection, changing audio routing or Stop all audio cancels it. Preview audio stays out of mix recordings.

Under **Saved DJ sets**, name the set and choose **Save new set**. This stores deck audio, positions, cues, beat grids, loops, pitch lock, tempo, EQ, filter/echo settings, deck volumes, crossfader, master volume and the four pad audio copies with their repeat, volume and follow-deck settings. Open set finishes any current recording, stops playback and restores the saved set paused. Headphone output device choices are not changed. Sets are stored on this device separately from Studio projects. Each save creates a new copy; later Studio edits or library removal do not change an existing set.

### DJ screen layout

The decks appear first, followed by the crossfader and master volume. Play, Stop, Headphones, Sync beats, Pitch lock, speed and volume stay visible. Open **Cues & loops**, **EQ & effects**, or **Tempo & beat grid** for their related controls. Active loops and changed effects are indicated in the collapsed headings.

**Browse tracks** jumps to the library; loading a saved track returns you to its deck. Playlist creation/reordering and saved-track removal are under **Manage playlists & tracks**. Pads, saved sets, saved recordings and headphone routing are below the mixer. Detailed DJ help opens from the Help button in the page header. Record mix and Stop all audio stay in the DJ header. The Studio playback footer is hidden while DJ mode is open.

### DJ help and MCP

The general Help page has one short DJ overview. Each main page has a Help button in its header with detailed guidance for that page: Home, Studio, My songs and starters, Drums, Melody, Pads, Sample Playground, DJ mode and Song notes. Help opens in a scrollable dialog without leaving the page. Close or Escape returns to the controls. DJ help covers loading, beat grids, cues and loops, effects, Studio pads, library management, headphones, recording, saved sets and MCP.

MCP 0.3.0 adds `get_dj`, `dj_load`, `dj_transport`, `dj_mix`, `dj_sync`, `dj_loop`, `dj_pad`, `dj_record` and `dj_set`. Ask the assistant to read `impulse-tracker://dj-guide` and inspect `get_dj` first. Deck and pad loading uses existing library audio or Studio sources; import new audio in the app. DJ actions apply live outside Studio Undo and song revisions. Headphone output selection, library/cue editing and recording export remain in the app. Reconnect your MCP client after updating its server package so it discovers the new tools. See [SETUP.md](../SETUP.md) and [DJ_GUIDE.md](../DJ_GUIDE.md) for setup and the supported workflow.

## Enable or pause the optional MCP connection

MCP is available in the desktop app and is optional. First follow `SETUP.md` in the desktop download to install the MCP package and configure a compatible client.

1. Open **Assistant activity** near **Save project**.
2. Click **Resume MCP**. The status changes from **Paused** to **Ready**.
3. Keep Impulse Studio open while your assistant uses it.
4. Click **Pause MCP** to block new requests.

Fresh installations start paused, and the app remembers your explicit choice across restarts. If your client reports “MCP is paused”, enable it in the app and retry. Pausing blocks new requests; it does not undo completed edits or stop music already playing.

Connect only clients you trust. A connected assistant can receive song data, track names and export paths, and its provider’s privacy settings apply. Studio edits support Undo; DJ controls act live outside Studio Undo. You can use all music features without enabling MCP.
