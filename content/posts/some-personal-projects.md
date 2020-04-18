---
title: "Personal Projects"
description: "An overview of some programming projects I've done."
date: 2020-04-18T11:11:52-04:00
draft: false
tags: [
    "JavaScript",
    "WebAssembly",
    "C",
    "Golang",
    "GameDev",
]
categories: [
    "Projects",
]
---

Here is an overview of some personal projects I've worked on over the years. Some are less complete than others. :)

## Flappy Birdy

{{< inlinetags JavaScript GameDev >}}

Very basic flappy bird clone made using JavaScript and the Canvas API. This is one of the oldest projects I've worked on, originally made sometime in 2014. It had issues but it worked! It makes me appreciate how much I've learned over the years.

{{< figure src="/images/flappy-birdy.png" alt="Flappy Birdy game screenshot" title="Those graphical assets were shamelessly taken from MapleStory." >}}

Back then, I was still pushing files to an FTP server directly by drag-dropping them via FileZilla. I had never even heard of Git. The only way I knew to do version control was by making a copy of my project and rename it to something like `project_2014_04_18`.

{{< extratag link="https://github.com/turnabout/flappy-birdy" icon="github" text="View on GitHub" >}}
{{< extratag link="http://kevinpageau.com/flappy-birdy/" text="Demo" >}}

## Space Invaders Emulator

{{< inlinetags C >}}

Simple emulator for the original Space Invaders arcade game. The entire thing aside from the tests is written in plain C. It uses the windows API to display the emulated VRAM's data on the screen to the user.

{{< figure src="/images/space-invaders-emulator.jpg" alt="Space Invaders emulator screenshot" title="It ain't much, but it's honest work." >}}

It was my first attempt at making an emulator. Very fun to make and a great learning experience. You naturally pick up on a lot of lower-level knowledge just by finishing such a project. It's interesting just for learning a little bit more about how a CPU works.

It also got me to appreciate unit tests since, without them, I would likely still be debugging the CPU instructions' emulation to this day.

{{< extratag link="https://github.com/turnabout/space-invaders-emu" icon="github" text="View on GitHub" >}}

## AWO

{{< inlinetags C WebAssembly GameDev >}}

AWO is an (unfinished) clone/port of Advance Wars. It's written in C and uses OpenGL & GLFW for rendering support.

{{< figure src="/images/awo-1.png" alt="AWO game screenshot" title="The game only has simple map editing functionalities so far." >}}


It's not meant to be an exact, "full" clone of Advance Wars. I essentially wanted to replicate multiplayer gameplay and eventually have it playable both in a desktop application and in a web browser, with online play capabilities.

In order to achieve this, I've made use of WebAssembly. The project was set up so you can compile it both with Visual Studio like normal to produce the desktop application, and with Emscripten to produce a WebAssembly binary embeddable in a web application. This way, the same exact code can be reused between your desktop and any web browser that supports WebGL. It's pretty cool!

OpenGL may sound overkill for such a small game, but... well, it might be. However! It actually ended up making certain things like palette swapping on the fly and zooming a bit easier. Here's a short demo:

<div style="width:100%;height:0px;position:relative;padding-bottom:66.667%;"><iframe src="https://streamable.com/e/9f270" frameborder="0" width="100%" height="100%" allowfullscreen style="width:100%;height:100%;position:absolute;left:0px;top:0px;overflow:hidden;"></iframe></div>

It's my most recent and largest project. It's far from finished yet, but I've made a good deal of progress. The core game engine was made to be as contained as possible and consumable by any external application. This external application can make use of the game engine by simply communicating with it through an API. I've made use of this structure to also create a secondary application that is a simple console utility that handles commands written by the user, transforms them in commands "understood" by the game engine and then sends them over to it. As a result, you can open this console utility, in which you can type commands to open a new game window, resize it, edit in-game values on the fly, etc.

The core game engine is containerized and lives in its own world. It doesn't know anything about where it's being included from and it doesn't need to. As long as it's being communicated with through its API, everything works as intended. Thanks to this, it becomes easier to port to different platforms, which is what I planned for (having the game playable both through an application and in a web browser).

It's still largely a work in progress and is not playable yet. It turns out making a game engine from scratch using C is a lot of work. :) It's also a bit on hold right now due to other work taking up more place. But I've loved working on this and will surely get back to it in the future.

Here's a small demo of the map editor. It shows off the algorithm that automatically determines which visual variation of tiles should be used when placing down a new one.

<div style="width: 100%; height: 0px; position: relative; padding-bottom: 66.667%;"><iframe src="https://streamable.com/s/ib698/vyuejl" frameborder="0" width="100%" height="100%" allowfullscreen style="width: 100%; height: 100%; position: absolute;"></iframe></div>

{{< extratag link="https://github.com/turnabout/AWO" icon="github" text="View on GitHub" >}}

## awodatagen

{{< inlinetags Golang >}}

This project generates the static assets used by AWO. It's a simple command-line utility written in Go.

I needed a tool to automatically generate the assets used by my game - the sprite sheet and all the game data. So I wrote it myself. It contains all the individually ripped sprites and visual assets used by the game. It goes through all of them, accepting it all as its input, then produces both the sprite sheet and a data JSON file as its output.

It works pretty well and it's very fast, thanks to Go. It uses a sprite sheet packing algorithm to automatically determine where sprites should end up. The project assets probably have over 100 individual sprite images and the resulting data file contains over 9000 (I'm not memeing, it currently sits at 9341) lines when not minified. Updating it by hand would be a nightmare!

{{< extratag link="https://github.com/turnabout/awodatagen" icon="github" text="View on GitHub" >}}
