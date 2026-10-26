# Audio plug-ins: smemplr, multidyn, smacheratr, para, widr, gentlr, dropr, moistr, probr, sweepr, tapr, pinchr, bubr

VST3 plug-ins for REAPER, Ableton Live and any other VST3 host on **macOS, Windows and Linux**. Free
to use, not for sale (see [LICENSE](LICENSE)). The current version is **0.32.0**.

| Plug-in | What it does for you |
|---|---|
| **smemplr** | Plays a sample from the keyboard. Loop it, slice it into hits, or warp it to the song tempo. A multi-mode filter, envelopes you can draw, an LFO, four modulation LFOs you drag onto any control, and an effects rack with up to 8 of the suite's effects in any order. |
| **multidyn** | Squashes or opens up 1 to 4 frequency bands at once: quiet detail comes up and loud parts are held down, band by band. The **OTT** style gives the loud, dense, over-the-top sound; **Character** is smoother. Side-chain input and a Sub band. |
| **smacheratr** | Adds warmth, grit or hard clipping. A pre-limiter stops transients from clipping harder than the rest, colour filters choose which frequencies saturate, and gentlr keeps a pushed sound from turning muddy or harsh. |
| **para** | A high-pass and a low-pass side by side. Pull them apart to carve a notch, then sweep it, fire it from MIDI notes, or use the **Vocal** movement, where the filter you move leads and fades the other out. Good for bass movement and filter sweeps. |
| **widr** | Makes a part very wide without falling apart in mono. Widrs in the same project share out the stereo field by role, so they do not all widen the same place. |
| **gentlr** | Keeps a mix clear by turning down mud and harshness only while they build up. Two bands plus a Sub and a High band, each cutting its region only while it is loud. |
| **dropr** | Slams a sound flat in 6 bands and drives it into a saturator. Negative ratios turn loud hits down below quieter parts, so a snare's body comes up and its snap is tamed. |
| **moistr** | Turns a dry bass (a detuned saw or a Reese, typically) into a wet, moving neuro texture: eight bell EQs sweep the low end against each other like rolling waves, and a level-matched saturator makes it crunch with a clean sub kept underneath (a resonant high shelf on a slow orbit is there too). After that it can split the sound into 3 or 4 moving bands: the low band held steady, the bands above it rising and falling on a seeded pattern, glued back with a compressor and a little grit, with an optional frequency shifter that never touches the sub. |
| **probr** | An analysis probe. Put one after each device or rack chain you want to understand, label each, arm them and play: each writes exactly what passes through it (the sound itself is untouched) with the song position, the tempo and any MIDI, into one folder per session on your computer. A script lines all the probes up by beat and compares what each stage of your chain does. |
| **sweepr** | Two EQ bands whose frequencies an LFO each sweeps, synced to the song or free, into a tape stage: drive into a fast leveller and a clipper, and highs that soften as the tape speed comes down. A boost and a cut moving against a bass in time with the beat, with the movement shown on the EQ curve. |
| **tapr** | A tape saturator: drive into a fast leveller and a clipper that holds the level, highs that soften as the tape speed comes down, and a three-band Cut EQ. The leveller and the EQ each go before or after the saturation. sweepr's tape stage on its own. |
| **pinchr** | A germanium compressor: a FET compressor with six knees, from a soft resistor to a hard Zener, into a germanium output stage whose Feedback adds gain and a resonant bass bump. Mix blends the compressed and the uncompressed sound, both through that stage. |
| **bubr** | A bass enhancer: a band at a frequency you tune (20 to 125 Hz), its focus set by Q-Factor, driven into a clipper (Intensity, Drive, Boost) and blended back with the dry sound, a gate keeping it to the louder parts, Low Cut, and a 0 dBFS limiter at the output. Measured setting by setting from a commercial bass enhancer, as a 1:1 model to start from. |

## Install

### Download the installer for your system

- **macOS** (Apple Silicon and Intel, macOS 11 or newer):
  [Plugins-macOS.pkg](https://github.com/bfielstr/audio-plugins-releases/releases/latest/download/Plugins-macOS.pkg)
- **Windows** (64-bit, Windows 10 or newer):
  [Plugins-Windows-x64-Setup.exe](https://github.com/bfielstr/audio-plugins-releases/releases/latest/download/Plugins-Windows-x64-Setup.exe)

Double-click the file and follow the steps. You can untick any plug-ins you do not want. They are
installed for every user on the computer, into `/Library/Audio/Plug-Ins/VST3/bfielstr` on macOS and
`C:\Program Files\Common Files\VST3\bfielstr` on Windows. Running a newer installer replaces the
older versions. Copies under the older names above (such as `Gently.vst3`) are removed, and so are
copies the one-line scripts put in your own user folder, so nothing shows up twice. On Windows,
uninstall from *Settings → Apps → Installed apps → Audio plug-ins (bfielstr)*.

### If your computer will not open the installer

The installers are not signed yet, so your computer may warn you the first time you open one. These
steps tell it that you trust the file you downloaded from this page.

- **macOS** says the installer "cannot be opened" or "cannot verify the developer": in Finder,
  right-click (or Control-click) the file and choose *Open*, then click *Open* again. If there is no
  *Open* button, go to *System Settings → Privacy & Security*, scroll down and click *Open Anyway*
  next to the message about the installer. Then enter your password.
- **Windows** shows a blue "Windows protected your PC" box: click *More info*, then *Run anyway*.

### One-line install scripts

If you prefer the command line, these do the same for your user only and also work on Linux.

**macOS** (universal: Apple Silicon + Intel) **and Linux** (x86_64):

```sh
curl -fsSL https://raw.githubusercontent.com/bfielstr/audio-plugins-releases/main/scripts/install.sh | sh
```

**Windows** (x64), in PowerShell. Run it as Administrator to install into
`C:\Program Files\Common Files\VST3`; otherwise it installs for your user only:

```powershell
irm https://raw.githubusercontent.com/bfielstr/audio-plugins-releases/main/scripts/install.ps1 | iex
```

The scripts download the latest [release](https://github.com/bfielstr/audio-plugins-releases/releases), check
its SHA-256 checksum and install the `.vst3` bundles into a **`bfielstr`** folder inside the standard
VST3 folder (e.g. `~/Library/Audio/Plug-Ins/VST3/bfielstr/`). Running a script again replaces the
installed versions. Copies that older installers put directly in the VST3 folder, and bundles under the
older names above, are removed. Only ours are touched: the vendor in the bundle is checked.

Options (environment variables): `SIMPLR_PLUGINS="Multidyn Tapr"` installs only some plug-ins,
`SIMPLR_VERSION=v0.25.0` picks a release, `SIMPLR_DEST=...` chooses the VST3 folder.

### Install by hand

Download the zip for your system from the
[latest release](https://github.com/bfielstr/audio-plugins-releases/releases/latest), unzip it and copy the
`.vst3` bundles you want into a `bfielstr` folder inside your VST3 folder: `/Library/Audio/Plug-Ins/VST3`
or `~/Library/Audio/Plug-Ins/VST3` on macOS, `C:\Program Files\Common Files\VST3` on Windows,
`~/.vst3` on Linux.

### After installing

In REAPER: *Options → Preferences → Plug-ins → VST → Re-scan*. In Live: *Settings → Plug-ins →
Rescan* (with *Use VST3 Plug-in System Folders* on).

## Licence

Free to use, not for sale: see [LICENSE](LICENSE) and [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). Questions, bug reports and requests: open an issue here.
