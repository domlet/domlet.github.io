---
title: "Sound Effects (Classroom Controller)"
date: 2025-07-06T00:00:20+0000
categories: [projects]
tags:
  [
digital art, audio, hack the classroom
  ]
description: Good trouble for the classroom.
toc: true
pin: false
image:
  path: /assets/img/th-domlet-soundboard8x8.gif
  alt: Press any button on the drum pad – hear a sound effect.
---

## What did I create?

This project uses a [Novation Launchpad MK2](https://www.google.com/search?q=Novation+Launchpad+MK2) MIDI controller to play 64 unique [sound effects](/posts/soundboard8x8/#what-sounds-does-it-play) in my classroom. Wanna see it working? [Watch this video demo](https://www.youtube.com/embed/3VgG6COkYkM) or [view the code](https://github.com/domlet/soundboard8x8) on GitHub.

## What problem does this solve?

I'm using purposeful and non-intrusive sound effects to...

1. Enable live game shows for 11th grade [MM/AN 40A: Intro to Game Design](https://peralta.curriqunet.com/DynamicReports/AllFieldsReportByEntity/18698?entityType=Course&reportId=314).
1. Illustrate the [Input-Processing-Output (IPO) Model](/posts/soundboard8x8/#the-input-processing-output-ipo-model) for 10th grade [AP CS Principles](https://apcentral.collegeboard.org/courses/ap-computer-science-principles).
1. Play music (30-sec, 3-min) for [classroom routines](https://www.google.com/search?q=why+are+classroom+routines+important+for+k12) like 'think time' and 'cleanup'.
1. Enhance attention, engagement, social bonding, and retention:

| **Neurochemical** | **Trigger**                                                  | **Function**                                           |
| ----------------- | ------------------------------------------------------------ | ------------------------------------------------------ |
| **Dopamine**      | Novel or rewarding sounds, success chimes                    | Motivation, reward learning, memory reinforcement      |
| **Oxytocin**      | Social or emotionally warm sounds (e.g., laughter, approval) | Social bonding, emotional safety, collaboration        |
| **Acetylcholine** | Task-relevant cues, attention-directing sounds               | Focused attention, neuroplasticity, sensory processing |

## What sounds does it play?

The board uses free sounds like these, from [Freesound.org](https://Freesound.org):

<iframe frameborder="0" scrolling="no" src="https://freesound.org/embed/sound/iframe/109662/simple/small/" height="30"></iframe>
<iframe frameborder="0" scrolling="no" src="https://freesound.org/embed/sound/iframe/341033/simple/small/" height="30"></iframe>

I use this [Google Sheet](https://docs.google.com/spreadsheets/d/1fiIznZn5HE2m4UhUrZ5vSpa5RvrzkZxwM9SHzO1GCRw/edit?gid=0#gid=0) to map the rows thematically, and generate code for [`soundMap.js`](https://github.com/domlet/soundboard8x8/blob/main/soundMap.js):

<iframe height="300" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vSxWSefMZE_2tYOPyjipr46D-nvkLu0SVs6LXJm_4q2rnnI7ajuLUXwTzt3Weg0cnhzYR2AxjvXVEEr/pubhtml?gid=1043225853&single=true"></iframe>

## How does it work?

![What is a controller?](assets/img/soundboard8x8/what-is-a-controller.png)
_A MIDI controller is like a video game controller – it sends signals to another device._

Well, the controller itself is just a bunch of buttons. As the name suggests, a **controller** IS NOT the same thing as a **computer**. Just like a game controller needs a game console (a computing device) and a game (a **program**) to do anything fun, a MIDI controller needs some kind of computer and program to make it do stuff.

| Term           | What It Means                               | Example                                        |
| -------------- | ------------------------------------------- | ---------------------------------------------- |
| **CONTROLLER** | A device for telling a computer what to do. | A PlayStation controller or Launchpad MK2.     |
| **COMPUTER**   | A machine that follows programs.            | A phone, tablet, laptop, or game console.      |
| **PROGRAM**    | A list of steps a computer follows.         | A game app or a website that shows your score. |

### The Input-Processing-Output (IPO) Model

So, I needed to write a **program** that would recognize the **input** (which specific button was pressed), and return a specific **output** (play the sound assigned to that button). When computers run programs like this (checking for a match), it's called **processing**.

![The Input-Processing-Output (IPO) Model](assets/img/soundboard8x8/input-processing-output-ap-csp.png)
_The Input-Processing-Output (IPO) Model describes how systems (like computing systems) work._

| Term           | What It Means                          | Example                                                |
| -------------- | -------------------------------------- | ------------------------------------------------------ |
| **INPUT**      | When you give the computer something.  | Pressing a button or clicking a mouse.                 |
| **PROCESSING** | What the computer does with the input. | Checking which sound is assigned to a specific button. |
| **OUTPUT**     | What the computer gives you back.      | Playing a sound or showing a message on the screen.    |

## How did I create it?

I tried to write this program the old fashioned way, using the [Web MIDI API](https://developer.mozilla.org/en-US/docs/Web/API/Web_MIDI_API) and [developer forums](https://forum.loopypro.com/discussion/49989/launchpad-programming). Two years passed.

Finally, I wondered how quickly I could accomplish my goal, so I asked ChatGPT:

> Use JavaScript and HTML to create a program that I can use in a web browser that recognizes my Novation Launchpad MK2 controller, and programs 3 unique sounds for the first 3 buttons on the top row.

By interacting with the service for a few hours, I was able to build [the app I wanted](https://domlet.github.io/soundboard8x8/). You can see [the code here](https://github.com/domlet/soundboard8x8/).

### Interactions with the service

```
> make the button LED lights blink a pattern upon initial connection between the web browser and the controller
[...]
> the sounds are not playing in the app when i run the local server. but the buttons do light up!
[...]
> move the sounds into a directory called sounds
[...]
> why does soundMap use 81 82 83 what do the numbers mean
[...]
> add the 8x8 grid back to the ui, make colors correspond to controller device colors -- unique color for each row
[...]
```

### Screenshot of the web app

[![Web app with an 8x8 grid of colorful buttons.](assets/img/soundboard8x8/soundboard8x8_screenshot.png)](https://domlet.github.io/soundboard8x8/)
_The resulting app included a user interface (UI)._

## What's next?

For in-classroom game shows, I need 3-4 "buzzers" for students playing as contestants. These are the considerations:

1. Contestants must stand about 4 feet apart from each other.
1. Buzzer hardware must be durable (so students can buzz energetically.)
1. There must be a buzzer 'window' triggered by the host (so contestants cannot buzz early.)
1. Only 1 contestant gets the opportunity (later buzzes not valid)

_Hopefully I'll find something on [Instructables](https://www.instructables.com/) or [GitHub](https://github.com/) that already works. USB Keyboards will probably be the first prototype. Wireless would be great, though. Wish me luck!_
