---
title: "Log Data Automation (Voice→Sheets)"
date: 2025-07-30T00:00:20+0000
categories: [projects]
tags:
  [audio, hack the classroom, tools, solving everyday problems, greatest hits]
description: Log structured data with voice commands only. 😇
toc: true
pin: true
image:
  path: /assets/img/th-domlet-voice-to-sheets-automation.jpg
  alt: Video tutorial for building a simple iPhone automation.
---

## What Problem Am I Solving?

As a classroom teacher, I use most of my time and energy teaching and managing students. I want to keep my attention focused on **maintaining a humane and optimal learning environment**. ❤️ So, it benefits both me and my students if I can avoid touching my phone, looking at my phone, or typing data into my phone.

So when I enrolled in a [year-long Professional Development course](https://teacherfriendly.com/courses/pedu-9011-creative-projects-for-the-classroom-1-6-credits/) that requires me to track 90 hours of my activities, I was determined to use **ONLY MY VOICE** to log my project time in a spreadsheet.

## What Did I Create?

Watch this [45-second demo](https://youtube.com/clip/Ugkx2Xjs6FSib-xUmofEa2jWv5Geqc3Di1iE?si=UQrQ0cVBRovk8JP6). That's the automation. :)

Then, I created [this video tutorial](https://youtu.be/GdIW5t9A8gQ) (below) as a project for said course ↓

<iframe height="450" src="https://www.youtube.com/embed/GdIW5t9A8gQ?si=mKephdnfMQdZ-Rvr&rel=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

I can activate the automation by saying _Hey Siri, Log Data_, and Siri asks me three questions. I answer the questions, and the data appears in three cells of a Google Sheet with an automatic timestamp:

![log snippet, 4 rows of data](/assets/img/voice-to-sheets-automation/log_snippet.jpg)

Here's the text of the interaction with Siri:

```
 Dom: Hey, Siri.
Siri: Hmmm?
 Dom: Log data.
 Dom: (Ignore this; I'll explain why.)
Siri: Category?
 Dom: Exercise.
Siri: Data?
 Dom: 10 squats.
Siri: Anything else to note?
 Dom: No.
```

I can't share a `.shortcut` file because anyone downloading those can be [pwned](https://www.google.com/search?q=Pwned+meaning+in+cyber+security) – and I can't share the shortcut's iCloud link because publishing my webhook would allow random people and bots to spew data into my personal spreadsheet. Ha! _So, watch the video and make your own._

## How Does It Work?

This automation uses a default iOS app (Shortcuts) to turn my spoken words into a JSON data object, and then sends it to Google Sheets by using the Webhooks service (now only for paying users) from the free IFTTT automation platform. The result is a simple spreadsheet with all my logged data in one place.

Here's a snapshot of the setup (including the webhook) in the Shortcuts app:

![scrubbed setup screenshot](/assets/img/voice-to-sheets-automation/webhook-json-scrubbed.png){: width="400" }
_Don't worry, I changed the Webhook after I posted the video._

<div class="box-info">
<div class="title"> What's a Webhook? Ask ChatGPT.</div>
A <strong>webhook</strong> is like a doorbell for apps. When something happens in one app, a webhook uses the Internet to go ring the doorbell (send a message) to another app – so that app can do the next thing.
</div>

## Security Risks

The word `key` should always signal **confidential** to you, as a web developer.

<div class="box-danger" markdown="1">
<div class="title"> API key</div>
A **`key`** is a unique identifier used to authenticate requests to a web service or API. In this case, you can see the key at the end of this Webhook:
https://maker.ifttt.com/trigger/practice_logging/with/key/`XXXXXXXkAmkw9DPXXXXXXX`
</div>

**If you publish or expose** your IFTTT Webhooks key, all your webhooks become hackable (random people or bots could activate any of your webhook automations – your light switches, SMS services, calendar items, emails...) Things could get [Black Mirror](<https://en.wikipedia.org/wiki/Shut_Up_and_Dance_(Black_Mirror)>) / [Twilight Zone](https://www.imdb.com/title/tt0734551/) for you.

1. Log into IFTTT > Services > Webhooks > [Settings](https://ifttt.com/maker_webhooks/settings) > Regenerate Key
1. Copy your new key (the one you just generated).
1. Disconnect, then reconnect each applet using Webhooks in IFTTT.
1. Update your apps or automations with your new webhooks key.
1. Check Google Drive; if you have duplicate files...
   1. Move your data into the newer file.
   1. Delete the older file.
1. Don't publish your new key!

### Common Data Security Levels:

| **Security Level** | **Possible Harm; Handling**                  | **Example**                |
| ------------------ | -------------------------------------------- | -------------------------- |
| **PUBLIC**         | No harm; OK to publish.                      | 🌸&nbsp; photo of a flower |
| **PRIVATE**        | Low harm; Exposure not recommended.          | 📧&nbsp; email address     |
| **CONFIDENTIAL**   | Harmful if disclosed; Do not expose.         | 🪪&nbsp; student records    |
| **SENSITIVE**      | Significant harm; Requires special handling. | 🩻&nbsp; health data        |
| **RESTRICTED**     | Severe harm; Strict access controls.         | 🔒&nbsp; trade secrets     |

## Psychology of Habits

![the habit loop is relaxed](/assets/img/voice-to-sheets-automation/habit-loop-is-cool.png){: width="400" }
_ChatGPT side-stepped my [basal ganglia](https://www.google.com/search?q=%22basal+ganglia%22+diagram) request. But the habit loop is chill._

Other ways to understand this automation are psychological and cognitive:

1. **My brain enjoys the 'beep' sound!** (Dopamine neurotransmitter spike goes _Wheeee!_.)

1. Automation makes my **task so small**, it qualifies it as an [Atomic Habit](https://www.goodreads.com/book/show/40121378-atomic-habits) (James Clear).

1. When habits are new, _whole brains work hard_. But, when habits become routine, brain activity shifts deeper, into the **basal ganglia**, near emotion and motor control. Brains go into "automatic mode" during the **habit loop**, conserving energy. [The Power of Habit](https://www.goodreads.com/book/show/12609433-the-power-of-habit?from_search=true&from_srp=true&qid=h47hXulPCZ&rank=4) (Charles Duhigg).

## Habit Loops and Teaching

Ultimately, this little automation should conserve my resources for the goal of teaching:

"**Automaticity is the advantage that independent learners have over dependent learners**," writes Zaretta Hammond, in [Culturally Responsive Teaching and The Brain](https://www.goodreads.com/book/show/23468051-culturally-responsive-teaching-and-the-brain) (133). As teachers, "We want to make these routines part of a **cognitive habit loop** that, over time and with repeated use, becomes automatic for the student."

| **Cognitive Routine**            | **Description**                                          |
| -------------------------------- | -------------------------------------------------------- |
| **Similarities and Differences** | Compare how concepts or objects are alike and different. |
| **Whole to Part**                | Break a whole idea into its key parts to understand it.  |
| **Relationships**                | Identify how ideas or events are connected.              |
| **Perspectives**                 | Consider multiple viewpoints on an issue or idea.        |

Look at me, practicing the _Relationships_ routine. 💅🏼

## Downstream Data Processing

The `category` value in the data structure enables me to coordimate different downstream automations or processes for the different workflows related to that category of data.

So, as an added benefit, I can use the same automation to track my diet (food intake) exercise habits, to-dos (tasks) and Jeopardy or Kahoot trivia questions for my students.

As a computer science teacher, I also help students anticipate how our data on the Internet can be 'sniffed' by bots, and used against us. ([That clip is here](https://youtube.com/clip/Ugkx1D-D-tVKhNB6u_xqjIdiWbTbzPr4lOKD?si=8kXRZ1-hnEdyCX5j).)

## Tools (to build the automation)

| Tool                                                                 | Cost         | Platform     | What it does                         |
| -------------------------------------------------------------------- | ------------ | ------------ | ------------------------------------ |
| [Shortcuts App](https://apps.apple.com/us/app/shortcuts/id915249334) | Free         | iOS, MacOS   | Voice transcription, GET/POST, JSON. |
| [IFTTT Webhooks](https://ifttt.com)                                  | (Not Free\*) | web & mobile | Create and program the Webhook.      |
| [Google Sheets](https://docs.google.com/spreadsheets)                | Free         | web & mobile | Stores the structured data.          |
| [Freesound.org](https://freesound.org/search/?q=beep&f=&d1=1)        | Free         | web          | Add a 'success' chime (optional).    |

_\*IFTTT removed Webhooks from the FREE services tier in 2024. 😢_

## Tools (to record the video tutorial)

1. Use [OBS (Open Broadcasting Software)](https://obsproject.com/) to record video tutorial.
1. Use [Black Hole](https://existential.audio/blackhole/) to record iPhone screen capture in OBS.
1. Use [obs-backgroundremoval](https://github.com/royshil/obs-backgroundremoval?tab=readme-ov-file) to remove my background in OBS.
1. Use [spacetypegenerator.com](https://spacetypegenerator.com/boost) to animate text.
1. Use [ezgif.com](https://ezgif.com/) to convert text video into looping GIF.
1. Use [YouTube](https://youtube.com) to host the uploaded video.
1. Use [YouTube Transcript Generator](https://www.youtube-transcript.io/) to generate video trascript.
1. Use [ChatGPT](https://chatgpt.com/) as a personal [gopher](https://www.google.com/search?q=what+is+a+gopher+gets+things+slang).

## Video Transcript

In case you are the `CTRL+F` type, or can't last 9 minutes w/o crashout. 😎

```
Hi, I'm Dom. I'm a classroom teacher and
um that means I'm really busy, but I'm
also trying to collect data all the time
um for myself, exercise, uh things that
I eat and professional development like
projects that I'm working on like my
time sheet. So, because I don't always
want to have my phone in my hand, um I
don't want to like open apps and like be
typing and stuff, I recorded this um
voice to spreadsheet automation using
iOS shortcuts and the if it service and
Google Sheets. So, I'm going to show you
how it works and then I'm going to show
you how to build it.
So um hey Siri
log data
ignore this I'll explain why
category
uh exercise
data
10 squats.
Anything else to note?
No.
Okay. So, you can see that the data
showed up right away and then I have my
automation automatically opening the
spreadsheet on my phone in case I do
want to make an edit or change
something. Um, so this is how it works
on iPhone. It uses the shortcuts app and
the shortcut is called log data. So I'm
going to click these three dots and here
are the steps. The first one is
automatically generated. You can't edit
it or delete it. You just ignore it. But
basically it means the shortcut is not
waiting for external data in order to
function. And then the second one is
pretty important. When I initiate the
shortcut with Siri, Siri wants to hold
on to the conversation. Um, but what I
want is to dismiss Siri because I want
my voice interactions to now be with the
shortcut.
This block is where I said ignore this.
I'll explain later. And here's the
explanation. 99% of the time there's a
bug where shortcuts will not play your
first speak block. But I want my first
speak block to say category. I don't
want it to be random. So, you have to
put some kind of block here to make the
app do something in order to make this
run. And I've tried play a sound, open a
file. Like, I've tried other stuff and
this is the one that works and I find it
very annoying, but it does the job. But
then, as you saw, we do something three
times. We have a voice prompt category
and then I get to say something that's
dictate text. And then I hold that thing
that I said or that string of characters
that is the text. I hold that text in a
variable called category. The second one
is called data. And the third variable
is called notes. And then here's where
the fun part happens. This block says
contents get the contents of a URL. So
basically we're not getting the method
is actually post. But this URL is
something that we'll program right now
to do something with the data that we
sent. And that data, the data category
and notes is packaged as a JSON object.
It's just a format of of characters and
letters. And then the shortcuts app
sends it over the internet to this web
hook. And then this web hook knows what
to do. I finish my interaction uh by
playing a sound beep and then opening
the spreadsheet. So here is how here's
how it works on
your computer. You're going to go to the
IFIT service which is free. You can
create an account. Um and we're going to
choose web hook. So this technology is
going to receive a web request. We're
going to call this practicing
practicing logging
and we'll create that trigger and then
we're going to have Google Sheets do the
next part. Now there's a certain amount
of risk to putting all of your
information on the internet and using
these free services. Um they are spying
on you on everything. So, in the future,
if you are logging that you eat
unhealthy foods or are taking risks,
there's some insurance company is
definitely going to try to deny you
health care or insurance. So, keep in
mind that they're sniffing like the
robots and the corporations are
generally and the government. Um,
anyway, it's not safe. So, uh, keep that
in mind. I'm going to call this
spreadsheet practicing logging. It's not
going to exist until this automation
runs. The first time it runs, it's going
to actually create this spreadsheet.
Sorry,
I just mentioned data sniffing. So, you
might need a moment to emotionally
recognize that
it sucks that nothing is actually free
and that they tell you it's free and
it's fun and it's easy and I'm probably
part of that.
But it's still good to learn how tools
work because this is how automations
work. You can use them to your
advantage, but you should always know
the risks.
Okay, back to the automation.
So, we're going to call this spreadsheet
practicing logging. And we're going to
give it three pieces of information.
Value one, value two, and value three.
this occurred at this is a timestamp
that is going to come from the if it
service itself. We could do it in the
shortcuts app, but it's nice to do it in
if it because if the shortcuts app is
broken, my shortcut gets messed up, I'm
troubleshooting it, it's still nice to
see the timestamps um because if it can
still do its part of the job even if
this is requiring troubleshooting. So,
I'm going to keep this. And then these
values are really sus because the values
we can see in the shortcuts app are
lowercase but these are uppercase. It's
annoying but this does actually work.
And then this event name we're not using
it. So I just delete it. These three
bars as you can see down here just
separate the cells. So one cell, two
cell, three cells. And then this path is
saying on your Google Drive where do you
want to put this new spreadsheet? If it
is opinionated, they want to put it in
these two folders. I'm just going to say
yes. Let uh let the service keep my
folders organized. I'm going to leave
the title. Same thing. Automated. You
could customize that. It's just a title.
So, when I click finish, that's where we
get the fun part down here. Now, we have
a web hook URL. I'm going to use this on
my phone. So to send it to myself, I
usually
text it on Google Voice and then here in
Google Voice, I grab my new web hook. So
I copied the link or the URL and then in
the shortcuts app, I'm going to click on
this plus. I'm going to create a new
shortcut. I'm going to give it a name
called rename
practicing logging.
Good. And then I'm going to select get
contents of URL. That URL is, you
guessed it, exactly what we just copied.
The method is going to be not get but
post. And then the request body I'm
going to use three text blocks. Text
text. Here they're going to be called
value
one,
value two.
value three. And here I'm not going to
take dictation. I'm just going to say
hi, bye.
Okay. Say done. I think that's going to
work. This file doesn't exist yet. So
when I go to recents,
the file does not exist. The spreadsheet
does not exist. But hey Siri,
practicing logging
just wants permission to open Chrome.
There it is. Now the spreadsheet exists
and it should say hi by we. Now I'm
going to tap this automation to run it
again.
There it goes. Hi by wee. One more time.
Hi by we.
So it works. You did it.
So I'm going to add some column headers
here because I want to know
what all these uh pieces of data are.
Every row represents an incident
represents something that we logged and
you don't want to use generic variable
names. So if your data is more
meaningful than hi by we, it will
probably say something like what did you
eat? Uh
is it a vegetable or dessert or whatever
and something else whatever you're
logging. Mine again says uh data
category and notes. Okay, that's it. It
works. I hope you have fun with that.
```
