# devlog #2 — window manager arc

**day 2**

the os grew a real window system today. everything is managed from one
`createWindow(app)` function, so adding a new app is just adding an object
with a name, an icon and a render function.

what's new:

- 3 apps now: about, notes, terminal
- close / minimize / maximize on every window (green button remembers
  your old size + position and puts it back)
- windows resize from a corner grip, focus raises them above the others
- a dock with the mac hover-magnify effect and little dots under
  running apps — minimized windows can be brought back from there
- notes autosave to localStorage as you type ("saving..." → "saved ✓")
- terminal got a tiny shell: help, neofetch, echo, ls, clear...

the dock magnify is just a css transform on hover:

```css
.dock .app:hover { transform: translateY(-9px) scale(1.18); }
```

one bug that cost me 20 minutes: the whole os went blank because i ended
the `neofetch` entry in the commands object with a `;` instead of a `,`.
one character. the browser console doesn't exactly spell it out for you.

small bonus: you can deep-link apps like `index.html#open=terminal,notes`,
which i mostly built so my screenshots are reproducible, but it's
actually pretty handy for sharing.

next: the apple-style dynamic island in the menu bar, a music player,
and a settings app to change the wallpaper.
