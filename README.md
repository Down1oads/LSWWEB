# LEGO Star Wars Web

Experimental PS2 static recompilation of LEGO Star Wars: The Video Game for desktop browsers.

Play at https://down1oads.github.io/LSWWEB/

On the first visit, select your own LEGO Star Wars: The Video Game PS2 USA v2.00 ISO
(1,869,316,096 bytes). The page copies it into this browser's private site storage,
so later visits start the game automatically without selecting it again. The disc is
never uploaded. To use a different disc or free the space, open
https://down1oads.github.io/LSWWEB/?change-disc and choose "Forget the stored disc"
(clearing the site's data also removes it).

Use current Chrome, Edge, or Brave with WebGPU and hardware acceleration. Click the
game or press a key to enable audio.

Tested: boot, title, Dexter's Diner, and Episode I chapter 1 through its intro
cutscene into gameplay at about 60 FPS with stereo audio. The rest of the game is
unverified; this is a work in progress, not a completed port.

The player keeps the original game logic and uses ps2-web-recomp, which statically
recompiles EE code to WebAssembly while modeling PS2 hardware and interpreting the
IOP. Upstream: https://github.com/snuri00/ps2-web-recomp. Its MIT license is included
in LICENSE-runtime.txt. LEGO Star Wars belongs to its respective rights holders; this
is an unofficial project.

Controls: see [CONTROLS.md](CONTROLS.md). Memory cards use browser storage; clearing
site data removes them. During play only the game and the green FPS counter are shown.

## Hosting

These are prebuilt static files served from the main branch root by GitHub Pages; no
build workflow is needed. The service worker supplies the cross-origin isolation
headers threaded WebAssembly needs, so a first visit may reload once. Serve over
HTTPS or localhost; opening index.html directly from disk will not work.
