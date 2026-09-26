# devlog #1 — it boots

**day 1**

started making my own os that runs in a browser tab. no frameworks, just
one html file, because i want to actually understand every line of it.

first build has:

- a boot screen with a logo + loading bar that fades away
- a frosted menu bar at the top with a live clock
- an aurora gradient wallpaper (just layered radial-gradients)
- one glass window ("about.txt") with mac style traffic lights

the fun part was making the window draggable. i used pointer events instead
of mouse events so it would also work if someone opens this on a phone.
the trick that made it feel smooth: instead of tracking where the mouse is,
i remember the offset between the cursor and the window corner on
pointerdown, then apply that same offset on every move. no jitter.

```js
bar.addEventListener('pointerdown', (e) => {
  drag = { dx: e.clientX - win.offsetLeft, dy: e.clientY - win.offsetTop };
});
```

next up: more windows, real minimize/maximize, and a dock.
