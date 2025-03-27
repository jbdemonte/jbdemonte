
# 🛠️ Side Projects

I've always loved building things — sometimes to solve a problem, often just for fun, and very often because I was curious to see *if* something was possible.

Since the late 90s (when I was coding games on a TI-80 calculator and poking around BASIC on an Amstrad CPC 464), I've created dozens of side projects — some polished, some scrappy, many deeply nostalgic. Over the years, that curiosity led me to build everything from Google Maps plugins (like [`gmap3`](https://github.com/jbdemonte/gmap3)) to barcode generators, retro gaming platforms, and emulation tools.

Some of these are still public and active, others are long archived, but every one of them taught me something and made me smile.

Today, I still love tinkering — whether it’s with old consoles I collect and repair, or with new ideas that mix tech, memory, and a touch of pixel art magic.  
I also contribute to [Recalbox](https://www.recalbox.com/), an open-source retro gaming OS.

---

### 🎮 [`Virtual Device`](https://github.com/jbdemonte/virtual-device) _(🔓 public)_
Simulate input devices (keyboard, mouse, gamepad, touchpad...) on Linux using [uinput](https://www.kernel.org/doc/html/latest/input/uinput.html).
Built in Go with a clean high-level API — perfect for scripting, automation, testing, or emulation.

While it has no visual UI (and no flashy screenshots to show off), this library shines in its simplicity.
You can create a full-featured virtual device with just a few lines of code:

```go
g := gamepad.NewXBox360()
err := g.Register()

...

g.Press(gamepad.ButtonUp)
g.MoveLeftStick(1, 1)
```

You can use it to emulate full virtual keyboards, touchpads, or gamepads from your own scripts.  
It’s a small, focused library designed to do one thing well: simulate input devices simply, cleanly, and in Go.

---

### 📺 CRT-TV Retro Gaming Platform  _(🕵️ not yet public — 🔒 classified retro tech!)_

This one started as a fun side experiment after I found [this CodePen CRT effect](https://codepen.io/GLITCHXploitR/pen/OxGKrq). I always wanted to build a private platform to share 80s–90s nostalgia with my family — not public, just a little time machine for us.

<p align="center">
  <img src="https://github.com/user-attachments/assets/3427fd34-ff13-41dc-a0c6-c21a57746655" alt="CRT-TV Screenshot" width="400" />
</p>

So I took that effect, cleaned it up, and built a 4:3 box to later model a proper cathode-ray TV frame.

Next, I embedded **Mesen** (NES emulator) compiled to WebAssembly. Simple setup: hit the power button, get screen static, wait 2s, then boom — **Super Mario Bros. 3** boots up like it’s 1991. At first, only keyboard input was supported.

Then came gamepad support (with a pretty ugly debug screen at that point 😅), and eventually a full SVG model of the **Philips TV** we had as kids. With the help of Claude (and not ChatGPT 😜), I turned a blurry photo into an animated SVG frame, complete with a glowing red LCD channel display.

I kept going:

- Built a full **TV UI** inside the screen to manage gamepad slots
- Made a dynamic game selector with cover art from a `gamelist.json`
- Designed an SVG **remote control**, fully functional with click/gamepad
- Added an OSD volume gauge because… why not
- Threw in **classic TV content**: A-Team, Hulk, test patterns, and some Easter eggs (Channel 11 👀)
- Moved Mesen to **Channel 7 (VCR)** — because obviously

Then things escalated:

- **Save states** with IndexedDB + screenshots
- **Drag & drop ROMs**, stored locally and shown in the game selector
- Modeled NES gamepads in SVG, synced to real-time inputs
- Refactored the entire UI into **canvas + WebGL shaders** for CRT realism
- Built a clean **video source manager** using a `useSourceRef()` hook (super proud of that one)
- Reported a WebGL context bug in Safari: [WebKit Bug #290436](https://bugs.webkit.org/show_bug.cgi?id=290436)

It now supports full mouse, keyboard, and gamepad input. Multilingual ready. Still completely local and private — a nostalgic love letter to the pixelated past.

What started as a simple nostalgic experiment quickly turned into a rabbit hole of ideas and features.  
Now, every new feature sparks three more. My todo list? Out of control — in the best way possible.

👉 [Online demo](https://jb.demonte.fr/wasm-tv)  
👉 [Devlog playlist (YouTube)](https://www.youtube.com/playlist?list=PLanKz10e7sIyxx8PWMDxf3mMb-0vX8RFo)

---

### 💾 [`Game Library`](https://github.com/jbdemonte/game-library-frontend) _(🔓 public)_

A browser-based retro desktop UI, just for fun.

This window manager is built with React, features draggable/resizable windows, and scrapes metadata for your games — all wrapped in a pixel-perfect, old-school interface.

👉 [Online demo](https://jb.demonte.fr/demos/game-library/)  
👉 [Read the article](https://dev.to/jbdemonte/create-a-window-manager-with-react-3mak)

<p align="center">
  <img src="https://github.com/jbdemonte/game-library-frontend/blob/main/screenshot.png" alt="Game Library Screenshot" width="400" />
</p>

---

Some older projects are no longer maintained — but you're welcome to browse the archives and dig through the bits and pieces I've left behind.
