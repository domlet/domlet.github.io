---
title: "Jeopardy-CSV (Free Classroom Game)"
date: 2025-08-03T00:00:20+0000
categories: [projects]
tags: [audio, hack the classroom, tools, solving everyday problems]
description: Drag-and-drop your CSV file to create a new game.
toc: true
pin: true
image:
  path: /assets/img/th-domlet-jeopardy-csv.jpg
  alt: Video tutorial for using a free online game platform.
---

- Click here to play the game: [Jeopardy-CSV](https://domlet.github.io/jeopardy-csv)
- Or, watch the [video tutorial](https://youtu.be/ntUGZEJkuoA).

## What Problem Am I Solving?

As a teacher, I need classroom games to be **FAST** and **CHEAP**. When I searched for platform to play a Jeopardy review game with my students, I reviewed the options from Research.com: [10 Jeopardy Game Maker Tools for Teachers](https://research.com/software/guides/jeopardy-game-maker-tools#10) (February 2025), but found none that met my criteria.

This is my **top requirement**:

> I want to prepare a CSV file with questions, answers, categories, and point values. Then, I want to upload that CSV file to automatically generate a new game.

There are my **red flags**:

- 🚩&nbsp; Costs more than $5 per year.
- 🚩&nbsp; Setup takes more than 10 clicks (or 10 minutes).
- 🚩&nbsp; Difficult to upload or download my own data.
- 🚩&nbsp; Visual complexity or unfamiliar UI patterns.

While [Factile](https://www.playfactile.com/), [Jeopardy Labs](https://jeopardylabs.com/), and [SuperTeacherTools](https://www.superteachertools.us/jeopardyx/) are all usable, I thought I might make something easier to use.

<div class="box-info">
<div class="title"> What's a CSV?</div>
A <strong>CSV</strong> file is like a spreadsheet, but simpler. It's a text-only file that stores data in rows and columns. Columns are separated by commas. Rows are separated by line breaks. View <a href="https://raw.githubusercontent.com/domlet/jeopardy-csv/refs/heads/main/sample.csv" target="_blank">raw CSV data</a> or download this <a href="https://domlet.github.io/jeopardy-csv/sample.csv">sample.csv</a>.
</div>

## What Did I Create?

With assistance from ChatGPT and GitHub Copilot, it took me about 2 weeks to deploy a [playable version of the game](https://domlet.github.io/jeopardy-csv), as I envisioned it.

## Video Tutorial

Naturally, I created a [video tutorial](https://youtu.be/ntUGZEJkuoA). I fix bugs while I record these tutorials, so recording is the long twilight of the development process.

<iframe height="450" src="https://www.youtube.com/embed/ntUGZEJkuoA?si=kNM7WRmL9bGLfwww&rel=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Development Notes

![test](assets/img/jeopardy-csv/css-is-awesome.jpg){: width="300"}
_If you know, [you know](https://blog.jim-nielsen.com/2021/css-is-in-fact-awesome/)._

## GIF

Here's a GIF showing the app's behavior and interaction design.

![Jeopardy-CSV game preview](assets/img/jeopardy-csv/jeopardy-csv-game-preview.gif){: width="400"}
_Notice how quickly you can begin a new game._
