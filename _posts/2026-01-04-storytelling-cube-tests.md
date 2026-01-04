---
title: "Storytelling Cube AR.js Test"
date: 2026-01-04T06:47:20+0000
categories: [projects]
tags: [game design, tools, AR, JavaScript]
description: Interactive dice in Augmented Reality?
toc: true
pin: true
image:
  path: assets/img/th-domlet-storytelling-cube-tests.gif
  alt: Click to see more books from this year's reading challenge.
---

I used ChatGPT and GitHub CoPilot to try some experiments with interactive 3D dice. You can see all the code in [this public repository](https://github.com/domlet/ar-test). Play with [the final result here](https://domlet.github.io/ar-test/index4.html).

## Let's use AR.js – index.html

[![AR Story Cube Demo](https://img.youtube.com/vi/oBnRrWEfwdw/0.jpg)](https://www.youtube.com/watch?v=oBnRrWEfwdw)

I wanted to teach my students how to create something like [57° North – an interactive AR storybook for the Merge Cube](https://www.mightycoconut.com/57north) but the Merge EDU platform was gatekeepy and required a [paid subscription](https://www.mergeedu.com/pricing/edu#compare). ([Twinery.org](https://Twinery.org) is free, open source, and web-based – so I may come back to that.)

So, I tried to use [AR.js](https://ar-js-org.github.io/AR.js-Docs/) to create a 6-sided cube that I could interact with using cube with the same [hiro marker](https://raw.githubusercontent.com/domlet/ar-test/main/img/hiro.png) on each side. I created some test markers [[1]](https://domlet.github.io/ar-test/marker.html),[[2]](https://domlet.github.io/ar-test/marker2.html) to point my camera at:

![demo hiro markers for testing](https://raw.githubusercontent.com/domlet/ar-test/main/img/demo-markers.gif)

**It did not work.** This was the concept:

1. A user can open [index.html](https://domlet.github.io/ar-test/index.html) on any device with a web browser and a camera. (Go ahead – try it now!)
2. The user must **give the app permission** to activate you device's camera and access the camera image. 
3. Then, the user should **point their camera** at the the [`hiro.png` marker](https://domlet.github.io/ar-test/marker.html). 
4. When the app recognizes the marker in the camera image, it should anchor the 3D experience on that marker. _But, it fails!_

### Why does it fail?

**AR.js** requires persistent visual recogniton of the hiro marker. So, if the marker turns ~90 degrees away from the camera on any axis, the app loses the anchor (and thus the AR graphics disappear). So, while the cube may have 6 sides conceptually, only ONE SIDE, plus a limited (angled) view of 4 other sides is available while the anchor is visible. **It is impossible** to see the 6th (back) side of the cube. Take a look:

[![AR Story Cube Demo](https://img.youtube.com/vi/yXGH10byikM/0.jpg)](https://youtube.com/shorts/yXGH10byikM)

## Can we fix it with UI? – index2.html

My next thought was... Well can I [add some UI elements](https://domlet.github.io/ar-test/index2.html) to help the user navigate the experience? This [felt too cumbersome](https://youtube.com/watch?v=a-QU9HRGdNo), so I abandoned the idea before developing the experience further.

I considered two alternatives:

1. **Using JavaScript for "marker handoff"** which means detecting when the `hiro.png` marker is rotated up, down, left, right...

2. **Using 6 unique markers** (one for each of the 6 cube sides) to load 6 different experiences – instead of 1 repeated single marker:

![hiro marker cube](https://raw.githubusercontent.com/domlet/ar-test/main/img/controller-paper-cube.jpg){: w="400"}

## Just use 3D (without AR) – index3.html

Finally, I ditched AR altogether and used **p5.js** to build an old-fashioned 6-sided cube in 3 dimensions, with different photo textures on each side. 

In [index3.html](https://domlet.github.io/ar-test/index3.html), you can double-click the cube to simulate a dice roll resulting in a single result – but I had an impossible time using CoPilot to script the trigonometry of the x/y/z axes to detect the result (which side of the cube is most visible to the user when the roll is finished). It didn't work well. 

Here's me, trying to train the model with my prompts:

```
when i see 6 console logs 5
when i see 2 console logs 2
when i see 3 console logs 3
when i see 3 console logs 5
when i see 1 console logs 1
when i see 4 console logs 4
when i see 3 console logs 4
when i see 6 console logs 4
when i see 6 console logs 4
when i see 5 console logs 5
when i see 4 console logs 3
when i see 6 console logs 6
when i see 2 console logs 2
when i see 1 console logs 3
when i see 1 console logs 1
when i see 2 console logs 3
when i see 4 console logs 5
when i see 3 console logs 4
```

As an alternative, I tried to have the roll function to pick a random side, and then simply **match the animation to the result** in that side facing the user...but it felt fake, and returned (`image6.jpg`) 100% of the time. I didn't like the idea enough to try fixing those things.

Frustrated, I tried to add a function that would **literally analyze the pixels rendered on the screen** – and detect which image is showing. (I assume this is resource-intensive, but I was willing to be greedy if it worked.) It was better, but still not good enough. Plus, if the images had similar compositions or color profiles, I imagined it could be even worse.

![6 different images for 6 cube sides](https://raw.githubusercontent.com/domlet/ar-test/main/img/6-sides.png)

### Attribution

1. image1.jpg - [Stockton Street Tunnel in Chinatown, SF (Google Maps)](https://www.google.com/maps/place/Stockton+Street+Tunnel/@37.7900488,-122.4069884,3a,75y,90t/data=!3m8!1e2!3m6!1sCIHM0ogKEICAgICOlJOELg!2e10!3e12!6shttps:%2F%2Flh3.googleusercontent.com%2Fgps-cs-s%2FAG0ilSzj6uOLVM7LysDZbFwmJJkGyYyxm7djAuzR6EbStmmKXHWmwkRkUl-fz_nJB96GQ68hXBQrilTamAKJUWFtzAuJwLYMYAxA4mamFvKvmPCcX-TlKW7hOW66WOAfzjFsM8L9Tsqr%3Dw397-h298-k-no!7i4032!8i3024!4m9!3m8!1s0x8085814e3120fe51:0x76667cad1895e919!8m2!3d37.7900488!4d-122.4069884!10e5!14m1!1BCgIgAQ!16s%2Fg%2F11gmyw8g5v!5m1!1e4?entry=ttu&g_ep=EgoyMDI1MTIwOS4wIKXMDSoASAFQAw%3D%3D).
2. image2.jpg - [Ring Nebula (Webb Space Telescope, NASA)](https://www.youtube.com/watch?v=L9MzlY7MVW0).
3. image3.jpg - [Lakeith Stanfield (Ryan Pfluger—The New York Times/Redux)](https://time.com/collection/time100-next-2021/5937674/lakeith-stanfield/).
4. image4.jpg - [Aprilia Tuono 457](https://storeusa.aprilia.com/tuono457.aspx).
5. image5.jpg - [La Bufa in Guanajuato, MX](https://www.google.com/maps/place/La+Bufa+Climb+-+Ruta+de+Ciclismo/@21.0002478,-101.2528348,1479m/data=!3m1!1e3!4m8!3m7!1s0x842b711e373b34b3:0xa479088f85c2aa71!8m2!3d21.0002478!4d-101.2502599!9m1!1b1!16s%2Fg%2F11nn3r6nrk?entry=ttu&g_ep=EgoyMDI1MTIwOS4wIKXMDSoASAFQAw%3D%3D) (my photo).
6. image6.jpg - [Flag of Oakland, California (Wikipedia)](https://mg.wikipedia.org/wiki/Sary:Flag_of_Oakland,_California.svg).


## Let's get out of here – index4.html

For my 4th version, I switched to ChatGPT and used the same approach. [It works better](https://domlet.github.io/ar-test/index4.html), but is still only about 80% accurate. Double click the cube to roll it 🔈:

<iframe width="500" height="450" src="https://domlet.github.io/ar-test/index4.html" title="index4.html" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


At this point, the code was out of my control. The app had **multiple functions** to detect the resulting face 😱 and, I had questions I could not answer:

  1. Were **user view** and **camera view** the same thing? I thought they were – so why would the function read the result of the roll so differently than my eyeballs did? 
  2. What is **negative z-index**? 
  3. What the nut 🌰 is **all this trigonometry** and these transformations?

This is when I threw in the towel:

  ```js
    // In view space, camera looks down -Z (common OpenGL convention).
    // So "most visible" means normal points most toward camera = most NEGATIVE z.
    let bestN = faces[0].n;
    let bestScore = Infinity; // we want smallest z

    for (const f of faces) {
      const tv = multMatVec3(m, f.v);  // transformed normal (approx; ok for pure rotations)
      const z = tv[2];

      if (z < bestScore) {
        bestScore = z;
        bestN = f.n;
      }
    }
    return bestN;
  ```

I know that I could understand the spatial math and the camera conventions if I set my mind to it. :)

But, I'm not that programmer. I help students explore game mechanics and experiment with novel digital instruments for storytelling and interaction. In the end, I like to know what's in the weeds, but that's not where I live. I'm now going to learn what we can build with just [Twine](https://www.youtube.com/watch?v=ZnARX2ToqYc&t=68s)!

I spent less than 24 hours on these experiments (and the writeup).
