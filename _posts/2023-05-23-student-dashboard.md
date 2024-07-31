---
# the default layout is 'page'
title: "Student Dashboard (Visual Countdown)"
date: 2023-05-23T16:47:20+0000
categories: [projects]
tags:
  [
JavaScript, web-based application, data visualization, solving everyday problems, Ed Tech, greatest hits, teaching
  ]
description: Visual countdown of the school year.
toc: true
pin: true
image:
  path: /assets/img/th-domlet-student-dashboard-1200x630.jpg
  alt: Srudents can easily see how close we are to the end of a term, or the next holiday!
---

## What is it?

- See the [live dashboard here](https://domlet.github.io/dashboard).

## Inspiration

Although our school publishes important dates on a public Google Calendar, **high school students do not typically use Google Calendar**. Instead, they ask me for information like I am Siri. 💀 I created this dashboard to foster student independence and reduce my own cognitive load. 😌

## What it does

This [Student Dashboard (Visual Countdown)](https://domlet.github.io/dashboard) is the startup webpage for computers in my classroom. It features the information I think students need most:

1. **The current date**, and day of the week.
1. **A visualization of all the days** of the school year, separated into terms.
1. **Student holidays**, such as teacher inservice days.
1. **Student activities**, such as Picture Day or basketball games.
1. **Important dates**, such as "Rosh Hashanah" or "Last Day of School".
1. **Opportunities**, such as free days at local museums.

## Why it's awesome

### Easy for staff to contribute

1. Retrieves events from multiple public Google Calendars and/or JSON.
1. Links to specific [Google slides](https://docs.google.com/presentation/d/1eIM1MJ_RYcnnu3raLXbotrhBV8nf2V1CfcmObazjeQs/edit#slide=id.g276f26a1cdb_0_0) (in a deck editable by teachers).

### Easy for students to use

![Desktop View](https://raw.githubusercontent.com/domlet/dashboard/main/images/qr.svg){: width="100" height="100" .right }

1. QR code (in footer) for easy sharing to student mobile devices.
1. Responsive design supports web or mobile clients.
1. Includes a link library for online student resources.
1. Built-in Google Translate widget for immediate translation.
1. Built in Google Calendar (combined display) for additional info.

### Easy for lab manager

1. Automatically refreshes every midnight.
1. Keeps computers awake with the `WakeLock` API.

## Tech stack

- JavaScript, jQuery, date-fns
- Bootstrap
- Google Calendar API
