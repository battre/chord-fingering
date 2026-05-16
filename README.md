# Piano Chord Visualizer — Interactive Chord & Fingering Diagrams

A free, interactive tool for building and printing piano chord & fingering diagrams. Designed for teaching kids and beginners.

## 👉 Use it online

**[https://battre.github.io/chord-fingering/](https://battre.github.io/chord-fingering/)**

No install, no signup — just open the link in your browser.

## What it does

- **Interactive keyboard.** Click any key to drop a marker. Click again to remove it.
- **Finger numbering.** Pick a finger (1–5) and click a key to label it. Pick `·` to label with the note name instead. Each finger 1–5 can only be on one key at a time — assigning it elsewhere clears the previous spot.
- **Keyboard shortcuts.** Press `1`–`5` to select a finger, `0` for the note-name marker.
- **Configurable range.** Set the visible keyboard range (default F3–G4, one octave).
- **C-key highlight.** Optional light-grey shading on every C, useful for orientation.
- **English / German.** Switch between English note names (`B`) and German notation (`H`, with `B` meaning B♭). Language is also encodable in the URL: [`?lang=de`](https://battre.github.io/chord-fingering/?lang=de) or [`?lang=en`](https://battre.github.io/chord-fingering/?lang=en).
- **Copy to clipboard / save as PNG.** Drop the current chord straight into a Word/Google doc, or download it as an image.

## Chord library

Below the interactive keyboard there is a small text editor with a domain-specific syntax for describing a list of chords. Each chord is then rendered as its own diagram with copy/download buttons. Useful for building a printable cheat sheet.

### Syntax

```
# Optional: fixed key range for all chords
range: F3-G4

# One line per chord: Title: Note[Octave]=Finger, ...
C Major: G3=5, C4=2, E4=1
A minor: A3=5, C4=2, E4=1
F Major: A3=5, C4=2, F4=1
G Major: G3=5, B3=3, D4=1
C7: A#3=3, C4=2, E4=1
```

- **Note**: `C, D, E, F, G, A, B` (or `H`). Accidentals: `#` (sharp) or `b` (flat). Examples: `F#4`, `Bb3`.
- **Octave**: integer, required. `C4` = middle C.
- **Finger**: `1`–`5`. Omit `=Finger` to display the note name instead.
- Both `B` and `H` are accepted for B-natural; `Bb` is B-flat.
- `range: F3-G4` (optional) sets a fixed key range for every chord diagram. Without it, each diagram auto-fits to its notes.
- Lines starting with `#` are comments. `#` after whitespace also starts a comment, so `A#3` is *not* mistaken for one.

### Append from the interactive keyboard

The **Append to library** button takes whatever you've built on the interactive keyboard, serializes it to the syntax above, and appends it to the library editor.

## Printing

Click **Print** (or use the browser's print command). The print view:

- Hides the editor, controls, and on-screen buttons — only the chord cards are printed.
- Lays the chords out in **2, 3, or 4 columns** (configurable via the *Print columns* dropdown).
- Avoids splitting a chord across two pages.

## License

Released into the public domain under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) by Dominic Battré. Free to use, modify, and redistribute for any purpose, no restrictions.

## Running locally

The whole app is a single self-contained HTML file. To use it offline, just download [`index.html`](./index.html) and open it in your browser.
