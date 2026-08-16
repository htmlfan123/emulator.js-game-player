# emulator.js-game-player

A minimal web-based ROM player using EmulatorJS (N64 core).

Important: This repository does NOT include any ROM files or ROM URLs. You must provide your own legally-obtained ROM and host it with CORS enabled.

## Features

- Minimal index.html that loads EmulatorJS and the N64 core
- No ROMs included — add your own ROM URL following the instructions below

## Quick start

1. Clone the repo:

   git clone https://github.com/htmlfan123/emulator.js-game-player.git

2. Serve the files with a local static server (example using Python 3):

   cd emulator.js-game-player
   python3 -m http.server 8000

3. Open http://localhost:8000 in your browser.

## How to add your ROM URL

Open `index.html` and set the `EJS_gameUrl` variable inside the script block. Example:

```js
// Path pointing to EmulatorJS data (already set in the file)
var EJS_pathtodata = 'https://cdn.emulatorjs.org/stable/data/';

// Set this to the direct URL of your ROM file (z64, n64, etc.). The host must
// serve the file with CORS headers (Access-Control-Allow-Origin) so the browser
// can download it from a different origin.
var EJS_gameUrl = 'https://your-host.example.com/your-rom-file.z64';
```

Then reload the page. If your ROM host blocks cross-origin requests, the game will fail to load.

## Change the core or title

- To change the emulation core (if you have a different core available via EmulatorJS), update `EJS_core` in `index.html`.
- Update the `<h1>` text in `index.html` to change the displayed title.

## Troubleshooting

- Blank screen / errors: Open the browser console and look for network or CORS errors.
- Ensure `loader.js` from the EmulatorJS CDN is loaded (the script tag is included in `index.html`).

## Legal / Ethics

Do not distribute copyrighted ROM files unless you are legally permitted to do so. Only use ROMs that you own or that are freely licensed.

## Credits

- EmulatorJS (https://emulatorjs.org)

