+++
title = "Personal Projects"
description = "Some of my personal programming projects."
+++

An overview of my personal projects - some of which are more complete than others. :)

## Space Invaders Emulator
Simple emulator for the original Space Invaders arcade game. The entire thing aside from the tests is written in plain C. It uses the windows API to display the emulated VRAM's data on the screen to the user.

![Space Invaders Emulator screen](/images/space-invaders-emulator.jpg)

It was my first attempt at making an emulator. Very fun to make and a great learning experience. You naturally pick up on a lot of lower-level knowledge just by finishing such a project. It's interesting just for learning a little bit more about how a CPU works.

It also got me to appreciate unit tests since, without them, I would likely still be debugging the CPU instructions' emulation to this day.

## AWO
AWO is an (unfinished) clone/port of Advance Wars. It’s written in C and uses OpenGL & GLFW for rendering support.

![AWO game](/images/awo-1.png)

It's not meant to be an exact, "full" clone of Advance Wars. I wanted to replicate multiplayer gameplay and eventually have it playable both in a desktop application and in a web browser, with online play capabilities.

In order to achieve this, I've made use of WebAssembly. The project was set up so you can compile it both with Visual Studio like normal to produce the desktop application, and with Emscripten to produce a WebAssembly binary embeddable in a web application. This way, the same exact code can be reused between your desktop and any web browser that supports WebGL.

OpenGL may sound overkill for such a small game, but it actually ended up making certain things like palette swapping on the fly and zooming easier to implement.

It was far from finished, but I had made a good deal of progress. However, it's unlikely I'll ever finish it. I had originally made it to try to fill a void left by the lack of Advance Wars games on the Nintendo Switch. However, Nintendo has since released Advance Wars Reboot Camp on the Switch, so I don't really feel the need to continue working on it.

