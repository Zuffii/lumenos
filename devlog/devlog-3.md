# devlog #3 — the island era

**day 3**

today was the fun one. i put a **dynamic island** in the top of the screen,
like the iphone. it's a black pill that sits over the menu bar and morphs:

- idle: small pill, shows a little equalizer + current track
- toast: puffs up to show notifications ("note saved ✓", terminal
  commands, wallpaper changes...)
- player: expands wide with prev/play/next buttons and a progress bar

all the morphing is one css transition on width/height with a bouncy
cubic-bezier, and the faces are absolutely positioned layers that fade in
based on a `data-face` attribute. way easier than it sounds.

```css
.island[data-face="player"] { width: 340px; height: 64px; }
```

the bigger news: **the music is real**. i didn't want to embed mp3 files
so the music app synthesizes lo-fi loops with the WebAudio api — triangle
wave chords, a sine bass, random pentatonic notes sprinkled on top, plus
a looped noise buffer filtered down for vinyl hiss. there are 3 "tracks"
(bpm + chord progressions) and a live frequency visualizer on a canvas.
no files, no copyright, just math.

also added:

- **settings app** — 4 gradient wallpapers, 4 accent colors (the island
  equalizer, dock dots, progress bars all recolor), saved to localStorage,
  plus a factory reset button
- **links app** — grid of glass cards
- terminal got an `open` command, so `open settings` launches apps
- island notifications wired into notes, terminal and settings

that wraps version 1.0. one html file, no frameworks, no login, and it
actually feels like an os. on to WebOS 2 🚀
