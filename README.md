# SkyLyrics

> **🤖 Vibecoded · 🔓 Open source (MIT) · 💸 Free forever**
>
> This mod was vibecoded: it was built by talking to an AI coding agent (Claude Code), not written line by line by hand.
> The full source code is in this repo under the MIT license. It's free, and it always will be: no paywall, no ads.

SkyLyrics shows synced lyrics for whatever song you're playing (Spotify, your browser, any media player) right in your
Minecraft world, and turns your music into a TikTok-style edit.

⚠️ **Photosensitivity warning:** edit mode uses flashing lights, rapid cuts and strobe-like effects.

## Features

- **Live synced lyrics** for the song you're playing, from [LRCLIB](https://lrclib.net). They can float on screen,
  scatter around, or hang in the world as 3D text you can fly through. There's a karaoke highlight and 9 fonts.
  Each song's timing can be nudged with `,` and `.`.
- **24 custom skies:** auroras, nebulae, black holes, synthwave, sunsets and more. They can change with every song.
- **Edit mode (B):** a fullscreen, music-synced edit.
  - **Space:** fly through 20 space scenes.
  - **Your world (N):** drone shots of your real world, cut to the beat.
  - **Song-aware director:** detects intro, verse, build-up, chorus, drop, break and outro, and edits each one
    differently (cut rate, scenes, transitions).
  - **Post effects:** glitch and datamosh, VHS, film grain, zoom blur, bloom, letterbox, a freeze frame and a speed
    ramp on drops.
- **Built-in TikTok recorder (F8):** records a vertical 1080×1920 clip of the game with the music.
- **Beat camera and Director's Clapperboard:** film cinematic drone takes of yourself.
- **Extras:** the Rhythm Disc rhythm game, the World Splitter (a portal to the Backrooms), the Disco Orb, the
  Universe Puller, a dad joke book and 20 spawn eggs of very normal guys.

## Requirements

| | |
|---|---|
| Minecraft | 1.21.11 (Java Edition) |
| Loader | Fabric Loader 0.20.1+ |
| Needs | [Fabric API](https://modrinth.com/mod/fabric-api) |
| Linux | ✅ Supported (PipeWire or PulseAudio; `busctl` and `parec` are normally already installed) |
| Windows 10/11 | 🧪 **Beta**, see below |
| macOS | ❌ Not supported yet (lyrics won't find your song) |

The F8 recorder also needs [ffmpeg](https://ffmpeg.org) installed and on your PATH.

### Windows beta

On Windows, SkyLyrics reads your song from Windows' media controls and listens for beats through Windows audio
loopback. Both use small PowerShell helpers that ship inside the mod. This part is **new and hasn't been widely
tested.** Please report what works and what doesn't. On Windows the F8 recorder saves video only, without audio, so add
the song when you edit.

## Install

1. Install [Fabric Loader](https://fabricmc.net/use/) for Minecraft 1.21.11.
2. Put `skylyrics-<version>.jar` and Fabric API in your `.minecraft/mods` folder.
3. Start the game, play a song, and press **Right Shift** for the settings.

To uninstall, delete the jar. Settings live in `.minecraft/config/skylyrics.json`.

## Keys

| Key | Action |
|---|---|
| Right Shift | Settings |
| J | Lyrics on/off |
| B | Edit mode on/off |
| N | Edit mode: space ↔ your world |
| F8 | Start/stop recording (9:16) |
| `,` / `.` | This song's lyrics earlier / later |
| `[` / `]` | Previous/next sky |

All of these can be rebound in Options → Controls. There's also a `/skylyrics` command.

## Privacy

- Song titles are sent to LRCLIB to look up lyrics, and album art is loaded from the player's art URL.
- Audio for beat detection is analysed in memory while edit mode, the beat camera or the rhythm game is on. It's never
  saved or uploaded.
- Recordings are saved only to your own `Videos/skylyrics` folder.

## Troubleshooting

- **No lyrics:** the song needs synced lyrics on LRCLIB, and your player needs to report it (Spotify does).
- **Lyrics are early or late:** use `,` and `.` while the song plays. The fix is saved per song.
- **Edit mode turns itself off:** your graphics driver couldn't compile the effects shader. The log is in
  `.minecraft/logs/latest.log`; search for `[SkyLyrics]` and open an issue with it.

## Multiplayer

The lyrics, skies, edit mode and recorder are all client-side. The items, blocks and spawn eggs need the mod on the
server too.

## Credits

- Built with [Fabric](https://fabricmc.net) and Fabric API.
- Lyrics come from [LRCLIB](https://lrclib.net), a free and open lyrics database.
- Fonts are from Google Fonts under the SIL Open Font License (see `licenses/FONT_LICENSES.txt`).
- **AI disclosure:** this mod was vibecoded with **Claude Code** (Anthropic's Claude models). The AI wrote the code,
  shaders and textures, and a human directed it, tested it and decided what to ship.

## License

The code is MIT licensed (see `LICENSE`): use it, fork it, learn from it. It's free.
