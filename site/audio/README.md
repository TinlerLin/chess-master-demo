# Built-in background music

These three original instrumental compositions were made for Chess Master using
only additive synthesis. They contain no recordings, samples, soundfonts, borrowed
melodies or third-party music. The composition and synthesis source is
[`scripts/generate-background-music.mjs`](../../scripts/generate-background-music.mjs).
The generated audio is distributed with this project under the project's terms.

| Piece | Length | Sound |
| --- | --- | --- |
| Windowlight / 窗边微光 / 窗邊微光 | 0:53 | Soft piano, warm chord bed |
| Quiet Garden / 静谧花园 / 靜謐花園 | 0:56 | Gentle plucks, sparse piano |
| Evening Tide / 暮色潮汐 | 1:00 | Warm ambient chords, distant piano |

To regenerate, install Node.js and FFmpeg with `libvorbis`, then run from the
repository root:

```sh
node scripts/generate-background-music.mjs
```

Optionally set `FFMPEG` to the FFmpeg executable path. Intermediate PCM WAV files
are written to `.temp/music-generation/`; the final stereo Vorbis files are
written here. The PCM synthesis is deterministic; Ogg container identifiers may
vary between encodes. Notes, reverberation and their tails wrap across each loop
boundary to avoid abrupt song fades. The single native browser music player
handles looping; exact transition timing depends on the browser's media decoder.

Music is off by default. Bundled files are only assigned to the audio element
when the user previews or plays, so selecting a piece alone does not fetch audio.
