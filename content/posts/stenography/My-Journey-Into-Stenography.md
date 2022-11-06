---
title: My Journey Into Stenography
date: 2022-10-18T21:53:10
image : https://imgs.search.brave.com/DUVAwv9X3C7uAsQNhax8Kpd1fiIM7UbajPmZ2tdyR5g/rs:fit:655:225:1/g:ce/aHR0cHM6Ly90c2Ux/Lm1tLmJpbmcubmV0/L3RoP2lkPU9JUC51/VDdEcDdiNGotbXdL/aFBxQmozbVJRSGFG/WCZwaWQ9QXBp
aliases:
    - /posts/my-journey-into-stenography/
libraries:
    - mermaid
tags: ['stenography']
---

Let me share my empowering journey of how I discovered and embraced stenography.
I have been using steno for all my interactions with a computer for nearly a
year.

Exclusive use starting January 1st, 2022. Who says new years resolutions can't
work?

I use steno for all my work as an embedded systems engineer and anything else I
do at a computer. Once you find the true power of stenography offers compared to
normal keyboard input, you can never go back.

## The Moment I First Heard Of Stenography And Plover

Soon after my second child's birth I was reading the monthly blog post from
[zsa](https://blog.zsa.io/2107-steno-tutorial/) while feeding my son a bottle.
I had purchased a [moonlander keyboard](https://www.zsa.io/moonlander/)
earlier that year and had been enjoying reading updates shared in these monthly
blogs. Most articles discuss changes to their firmware builder web interface or
mention of adding some new feature. I was not expecting a fundamental change to
how I use a computer and would cause me to never use a normal keyboard again.

I couldn't wait for my son to finish this bottle so I could check this out.

{{< featuredImage alt="featured image" width=400 height=300 >}}

The life changing article titled
[Stenography with ZSA Keyboards: A Tutorial](https://blog.zsa.io/2107-steno-tutorial/)
by [Paul Fioravanti](https://www.paulfioravanti.com/). I love
tools and expanding my power user arsenal. I knew right away I needed to try
stenography. I'll share some quotes from the article that stuck out to me and my
thoughts on them.

> potential to supercharge your speeds past 200 (or even past 300!)
> words-per-minute:

This can't be possible right... How have I not heard of this before? Those
speeds seem unreal!

> Open up a text editor and press the steno E key (near your right thumb), and
> if it outputs “he”, then you have steno working! Try pressing some of the other
> keys, as well as chording some keys together, and see what output you get!

Wow! Words with key chord presses? I did try this right away and found
instantaneous joy. It brought me a similar feeling as the first time I used a
microcontroler to blink and LED. Steno is such a different concept than typing
on a normal keyboard.

> Now comes the part that will involve a lot more time and effort: learning
> stenography.

This makes perfect sense, anything that contains true power take time and effort
to learn.

> Learning stenography feels more like learning a new language, rather than just
> a new keyboard layout, and so consequently it will likely take some time and
> practice before you start to reach a basic level of competency.

Nothing with this remark is to scare or mean it will be difficult . This is well
written advice and helps to set start expectations.

> I sincerely hope that this post has gotten you at least a bit steno-curious
> about the potential of using your ZSA keyboard beyond a standard QWERTY layout.

I'm more than a little curious... Where is my computer?? I watched the
video at the end and then reread the article over and over to make sure I
didn't his some important detail. It all seemed fanciful and incredible. I knew
I must get to work and learn more for myself.

## What Is It Like Learning Stenography?

Learning stenography takes work. The work of stenography is mental work. It
requires thought to type anything. There will be no muscle memory to lean on,
and it will take weeks or months before you may have the skill to type an entire
sentence without looking something up.

Since stenography uses methods such as phonetic phrasing and briefs to create
words it takes some thinking. Let me share some words and phrases and the
thoughts you'll need to process to write them.

To write the phrase `Take your vitamin` consider these thoughts you may
have in an interview with your brain:

(graphs made using [mermaid](https://mermaid-js.github.io/mermaid/#/flowchart))

```mermaid
sequenceDiagram

me ->> brain: Does the word "take" have a brief?
brain ->> me: No, it should be phonetic
me ->> brain: How do I form the word "take" by sounds?
brain ->> me: Use a starting "t" sound with a long "a" and ending "k" sound
me ->> brain: The long "a" sound uses the keys AEU and not just A right?
brain ->> me: Yes, indeed AEU for a long "a" sound
me ->> brain: Okay, I got the starting "t" and long "a" sounds. How do I chord the ending "k" again?
brain ->> me: Ending "k" sound is made by pressing both "BG"
me ->> brain: Okay I got it, I'll chord take by pressing TAEUBG keys and then releasing
me ->> brain: Does the word "your" have a brief?
brain ->> me: No
me ->> brain: I know that the starting "y" sound is chorded KWR, how do I form the "o" sound?
brain ->> me: Usually you should use just U, but using OU causes less problems
me ->> brain: Okay I'll chord it use KWROU + ending R
me ->> brain: The word vitamin seems simple enough to sound out, let's try
me ->> brain: How do you chord a starting "v" sound?
brain ->> me: Use SR
me ->> brain: Okay then I need a long "i" sound which uses AOEU
brain ->> me: Don't forget the ending "t" sound
me ->> brain: Okay I'll chord it with SRAOEUT
me ->> brain: But I'm not done, I need a min ending chord
me ->> brain: Starting "m" sound + short "i" vowel + ending "n" sound
me ->> brain: PH forms the "m" sound, EU forms the "i" sound, how to do ending "n"
brain ->> me: PB forms the right side "n" sound
me ->> brain: Okay I'll use PHEUPB making SRAOEUT/PHEUPB for the full word vitamin
```

Stroke summary:

- TAEUBG - take
- KWROUR - your
- SRAOEUT/PHEUPB - vitamin (the slash shows that it takes two stroke)

To write the phrase `You'll always sound precocious ... supercalifragilisticexpialidocious`

```mermaid
%%{init: {'theme':'dark'}}%%
sequenceDiagram

me ->> brain: Does the word "you'll" have a brief?
brain ->> me: Yes, this one is from Learn Plover! top 100 briefs it is "UL"
me ->> brain: Okay, I'll stroke "UL"
me ->> brain: Does the word "always" have a brief?
brain ->> me: Probably... But I bet you could do it phonetically
me ->> brain: Okay I'll try, let's start with stroking "AUL" like the word all
me ->> brain: Then let's add "WAEUS" for the word ways. Shoot that gives "all ways"
me ->> brain: Uh-oh! Maybe I could use my dictionary mapping to join the words
brain ->> me: Yeah, try it. As suggested on the Plover wiki it is "TK-FPS":"{*!}"
me ->> brain: Okay let's stroke "AUL/WAEUS/TK-FPS". Uh-oh, that gives allways
me ->> brain: It is almost correct, just an extra "l"
me ->> brain: Should I use my arrow key mappings to go back and edit the text?
brain ->> me: DON'T YOU DARE! THAT IS NOT AWESOME, JUST LOOK UP THE WORD!!!
me ->> brain: Okay, okay fine. I'll stroke "PHR*UP" to use my Plover lookup
me ->> brain: Hey look, if I had used "AL" instead of "AUL" I'd have had it!
me ->> brain: But, look there. I see a brief for always stroked "AULS"
brain ->> me: Okay, I'll remember that for next time. This word is common.
me ->> brain: I'll stroke PW-FP to backspace 9 times after doing the Plover lookup
me ->> brain: Normally you can chord the * key to delete entire words
me ->> brain: Does the word sound have a brief?
brain ->> me: No, just phonetic I'm pretty sure
me ->> brain: Okay let's use starting "s" sound, "ou" middle with "n", and "d"
brain ->> me: Nice, using the stroke "SOUPBD" worked!
me ->> brain: Precocious looks too complicated for a brief, let's go phonetic
brain ->> me: Hey, you could use a prefix for the "pre" starting letters
me ->> brain: Okay, I'll stroke "PRE" and then next stroke needs "k" to start
me ->> brain: And a long "o" middle
me ->> brain: How can we make the "shus" sound?
brain ->> me: Stroke RB for the "sh" sound, and adding S to the end should work
me ->> brain: Okay let's stroke the whole word "PRE/KOERBS"
brain ->> me: Look, it worked! You're getting the hang of this!
me ->> brain: How can I do the punctuation and spacing combo " ... " ?
brain ->> me: Use you're mapping from emilys-symbols
me ->> brain: Right, that is perfect. Okay I'll stroke my unique starter SKWH
me ->> brain: I want a space on both sides of the output so I'll add AO to the stroke
me ->> brain: Add R to the stroke to get the period, and add T to get three
me ->> brain: Okay in total I'll stroke "SKWHAORT"
me ->> brain: How on earth will I stroke supercalifragilisticexpialidocious??????
brain ->> me: Remember, we learned this from typey-type's steno-party-tricks dictionary
me ->> brain: Oh, right. I've yet to show this off at a party but I remember now
me ->> brain: I remember the brief sounds like "Sfraj" so stroke like "STPRAPBLG"
```

Stroke summary:

- UL - you'll
- AUL/WAEUS - ~~all ways~~ misstroke (stenography term for a typo or accident)
- PW-FP - for backspacing
- AULS - always
- SOUPBD - sound
- PRE/KOERBS - precocious
- SKWHAORT - `...`
- STPRAPBLG - supercalifragilisticexpialidocious (NOTE: this word is in default
  Plover dictionary as well)

Referenced links:

- [Plover retro actively delete space](https://github.com/openstenoproject/plover/wiki/Dictionary-Format#retroactively-delete-space)
- [typey-type steno-party-tricks dictionary](https://didoesdigital.com/typey-type/dictionaries/lessons/drills/steno-party-tricks/steno-party-tricks/)
- [emily-symbols](https://github.com/EPLHREU/emily-symbols)
- [my modded version of emily-symbols that affects spacing](https://github.com/derekthecool/PloverStenoDictionaries/blob/ffef83bd5177ef1d81063ed54ab3c0219108e047/plover/emily-symbols.py)

## What Can Stenography Do?

There are many everyday uses for stenography. In fact, the real question should
be why can't my qwerty keyboard do more?

You can use a steno keyboard for anything that you'd use a computer for. Here is
a list of things I use stenography for.

- Writing emails
- Writing code
- Opening programs on my computer
- And everything else that I need a computer for

### Control Your Computer

Steno should not be compartmentalized to just text fields. To truly unleash the
abillity to use steno exclusively and ditch using qwerty we need to control our
computers. If it becomes a burden to switch from your steno keyboard to your
mouse or to another keyboard find a way to do those tasks with steno.

If you are still using your mouse to close programs by pressing the little
button in the corner, STOP! Use a steno mapping for that. For example Windows
users could make a dictionary entry for `ALT+F4` to close the window your in.
Get creative!

One way to have more fine grained control over your computer window management
is to use a window manager. I personally use [workspacer](https://workspacer.org/quickstart/)
for Windows use and [AwesomeWM](https://awesomewm.org/index.html) for Linux.
While both of these work great upon first install, knowing the programming
language they are configured in helps. I happen to be lucky by already knowing
csharp and lua which are used in workspacer, and AwesomeWM.

I don't use mac, but a quick search engine result gave me a good
[reference](https://alternativeto.net/software/i3/?platform=mac) that
includes several viable options.

### Programming With Stenography

I plan to write many more articles about this. Speaking from over a year of
experience I can say this it is possible and it is glorious! I spend a lot of
time at my computer working on programming, using steno while I work has made
any wrist or arm pain disappear.

### Oh, And Don't Forget The Obvious One... Writing Normal Text Fast

This one cannot be left out. One great source of power from steno is the speed
it can offer. But I must say that my current speed is still not very high at
around 50 WPM. It is important to not get carried away by only caring about
speed.

### Spelling

I find the spelling benefits far out weigh the speed benefits. Not having to
worry if you put right amount Ls in the word `specifically` feels nice.
The spelling benefits are very noticeable with the single key briefs. It might
sound not very important, but I've never misspelled these words using steno:

- the
- and
- had
- he
- you

If you see someone misspell the word `the`, you may consider kindly
suggesting stenography to them.

## Summary

Stenography is amazing and I think everyone should use it!

Truths I've found about stenography

- Stenography is not expensive thanks to [Plover](https://www.openstenoproject.org/plover/)
- Plover is free and Open Source software. You can get started with Plover with
  the only cost being your keyboard.
- Plover was started by [Mirabai Knight](http://plover.stenoknight.com/) when
  she was frustrated with expensive, closed source stenography! Thank you
  Mirabai for doing something about your frustration and creating Plover!
- Learning stenography is fun and requires continuous learning
- Stenography is ergonomic and can ease wrist pain

What are you waiting for, try it out today by reading the guide
[Beginner's-Guide:-Get-Started-with-Plover](https://github.com/openstenoproject/plover/wiki/Beginner's-Guide:-Get-Started-with-Plover)!
