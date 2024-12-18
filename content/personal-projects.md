+++
title = "Personal Projects"
description = "A quick look at some of my side projects."
+++

A quick look at some of my side projects. Note that most are a bit old, but I still think they’re worth mentioning.

## InterviewQs

[InterviewQs](https://interviewqs.com) is an online platform used by data scientist professionals to practice for job interviews. It features a large collection of data science interview questions, categorized by topic and difficulty level.

![InterviewQs home page](/images/interviewqs.png)

I joined forces with two talented data scientists who founded the platform. I’m responsible for the development and maintenance of it, as well as the creation of new features.

Over the years, I created:

- The entirety of the current website stack
    - Next.js/TypeScript
    - Go backend
- A newsletter system, implemented in Go and running on an AWS Lambda. Responsible for sending out the correct question emails to the correct users.

I also migrated 400+ interview questions from a legacy collection of Pug files with redundant HTML into a clean, structured Markdown format. That was pretty fun.

## Space Invaders Emulator
Emulator for the original Space Invaders arcade game. The entire thing aside from the tests is written in plain C. It uses the Windows API to display the emulated VRAM’s data on the screen to the user.

![Space Invaders Emulator screen](/images/space-invaders-emulator.jpg)

It was my first attempt at making an emulator. Very fun to make and a great learning experience. You naturally pick up on a lot of lower-level knowledge just by finishing such a project. It’s interesting just for learning a little bit more about how a CPU works.

It also got me to appreciate unit tests since, without them, I would likely still be debugging the CPU instructions’ emulation to this day.

[View the source code on GitHub.](https://github.com/turnabout/space-invaders-emu)

## AWO
AWO is an (unfinished) clone/port of Advance Wars. It’s written in C and uses OpenGL & GLFW for rendering support.

![AWO game](/images/awo-1.png)

It’s not meant to be an exact, “full” clone of Advance Wars. I wanted to replicate the multiplayer gameplay and eventually have it playable both in a desktop application and in a web browser, with online play capabilities.

In order to achieve this, I made use of WebAssembly. The project was set up so you can compile it both with Visual Studio like normal to produce the desktop application, and with Emscripten to produce a WebAssembly binary embeddable in a web application. This way, the same exact code can be reused between your desktop and any web browser that supports WebGL.

OpenGL may sound overkill for such a small game, but it actually ended up making certain things like palette swapping on the fly and zooming easier to implement.

It was far from finished, but I had made a good deal of progress. However, it’s unlikely I’ll ever finish it. I had originally made it to try to fill a void left by the lack of Advance Wars games on the Nintendo Switch. However, Nintendo has since released Advance Wars Reboot Camp on the Switch, and someone else already made a successful project similar to it.

[View the source code on GitHub.](https://github.com/turnabout/awo)
