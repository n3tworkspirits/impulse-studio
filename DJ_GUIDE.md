# DJ mode through MCP

Call get_dj before making changes. It returns decks, transport, BPM, rate, cues, loops, effects, mixer, pad assignments and metadata for local tracks, sets and recordings. List offset/limit defaults to 0/50, maximum 100. Audio bytes are never returned. Studio source IDs are also listed.

DJ controls act live and are outside Studio Undo and expectedRevision. They do not edit the Studio song. Load/clear replaces a deck; opening a set replaces the current DJ session and finishes recording. Get the musician's intent before replacing work or starting playback/recording. The desktop app must remain open. Mutating tools enter DJ mode; switching to another workspace stops DJ playback. Stop Studio recording before DJ actions.

1. get_dj to inspect sources and loaded decks.
2. dj_load with deck A/B and exactly one trackId or studioId. Studio sources render independent audio copies; reload after editing Studio. Local file import remains in the app. No streaming or arbitrary file paths.
3. dj_transport with deck A/B and play/pause/stop/clear. All supports pause/stop only. Stop all stops pads/previews and finishes recording.
4. dj_sync follows the other deck's effective BPM and beat grid. Correct unknown/wrong grids in Tempo & beat grid in the app first. Variable-tempo music may drift.
5. dj_mix sets deck volume, rate, pitchLock, low/mid/high EQ, filter, echo and echoBeats; deck fields require A/B. crossfade and master are global. Pitch lock preserves deck pitch; extreme changes can introduce artifacts.
6. dj_loop starts a beat loop or exits it. Start requires beats and known BPM. Cues and manual loops remain editable under Cues & loops in the app.
7. dj_pad loads a section/saved loop by studioId, plays, stops or clears pad 1–4. loop selects repeat versus one-shot. Play is explicit, not a toggle. Pads launch on the selected deck's next beat; their pitch follows tempo. Pad follow-deck and volume remain in the app.
8. dj_record starts or finishes an on-device main-mix recording. Includes deck effects and pads, excludes headphone previews. Export in Saved recordings in the app. New recordings preserve the stereo master as lossless 32-bit float WAV at the audio context sample rate. Limit: two hours or the WAV size limit. Older compressed recordings remain supported; only those over 30 minutes require Original audio export.
9. dj_set saves a new named set or opens an id from get_dj. Sets preserve deck audio, cues, loops, positions, effects, mixer and pad copies. Restores paused and leaves headphone device routing unchanged. Sets are local and separate from Studio project files.

Use Audio routing & headphones in the app for separate devices or a DJ splitter. Library headphone preview stays out of recordings. Search, favourites, playlist editing, removal/undo, recording export and file imports remain in the app. None of these tools grant arbitrary filesystem or output-device access.

After a timeout, inspect get_dj and the app before retrying; a live action may already have happened. For a save, inspect the set list before repeating to avoid duplicates. If bridge dispatch is disabled after timeout, restart the desktop app first.
