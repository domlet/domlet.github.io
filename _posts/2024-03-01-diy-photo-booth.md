---
title: "DIY Event Photo Booth for $30"
date: 2024-03-01T00:00:20+0000
categories: [projects]
tags: [solving everyday problems]
description: Just an iPad + tripod + app.
toc: true
pin: true
image:
  path: /assets/img/th-domlet-diy-photobooth-1200x630.jpg
  alt: Photobooth outtakes are beautiful everyday things
---

## What Problem Are We Solving?

At our school, we like to have a photo booth to record group pictures at events. This solution shows how you can enable a basic self-service (or attended) photo booth using an iPad and a paid app on a tablet.

## Materials

- iPad
- 1 month paid subscription to [Simple Booth](https://buy.simplebooth.com) $30
- tripod with tablet attachment
- lightbox
- extension cord
- backdrop (optional)

## How it Works

In the photo booth, visitors can touch the tablet screen to take their own photos within the Simple Booth app. Then, visitors can scan a code or enter their phone number/email to send the photos to themselves. Printing photos is possible, but requires more preparation (not covered in this guide).

## Setup

1. On your tablet, log into the app and pay for 1 month.
1. Customize your template and settings for your event.
1. Set up tripod, backdrop, and lightbox.
1. Stand nearby to help people use the app. :)
1. After the event, log into [Simple Booth](https://buy.simplebooth.com) and download all the photos to your computer.
1. Cancel your subscription in the app so you don't get charged for another month.

## File Management

Use this bash script to enhance the filenames (replace `photobooth-2023-winter-social` with your event and date):

```bash
a=0
for i in *.jpg; do
  new=$(printf "photobooth-2023-winter-social_%03d.jpg" "$a")
  mv -i -- "$i" "$new"
  let a=a+1
done
```

![Thumbnails from photobooth, low-resolution](assets/img/diy-photobooth/diy-photobooth-lowres.png)
_A lot can happen in an 8x8 booth._

## Photo Releases

If you plan to publish images or use them in printed or distributed materials, obtain media releases from your participants:

- [media-release-form-adult.pdf](assets/img/diy-photobooth/media-release-form-adult.pdf)
- [media-release-form-minor.pdf](assets/img/diy-photobooth/media-release-form-minor.pdf)
