---
title: Intro to Linux and FOSS
date: 2025-09-09
categories:
    - Tech
---

Presented to you by the
<img src="/assets/ocf-box.png" style="width:200px;float:center;margin:10px;">

<img src="/assets/linuxtm.png" style="float: center;">

<!-- more -->

## The Shell

The shell is a command line-interface (CLI) to interact with a computer.

Common shells include: bash, zsh, fish

>Tip: if you don't know if you're using zsh or bash, run `echo $0`

Basic command structure:
`[command] [flags] [arguments]`

- ex: `ls -a ~/`
    - `ls`: lists the contents of a directory
    - `-a`: do not ignore entries starting with .
    - `~/`: your user's home directory

Common shell commands:

- `cd` - change directory
- `ls` - list directory
- `cat` - concatenate and print files
- `head` - read the first 10 lines
- `less` - read larger files
- `mv` - move
- `cp` - copy
- `rm` - delete a file 


And so many more... if you don't know the command for something, look up "how to ___ linux".

- ex. I want to unzip a file. Search "how to unzip a file linux", check Stack Overflow and see that you use the "unzip" command. Realize I don't have the unzip utility installed. Install it with my distro's package manager, profit.
- The common shell commands above are part of the "GNU Core Utilities"

Text Editors

- Vim
- Nano
- Emacs

<img src="/assets/xkcd.png" style="float: center;">

You'll learn more in today's lab.

## How did linux come to be?

GNU/Linux: Linux is the kernel of the OS, GNU is other crucial software (ex. Gnu Coreutils)

<img src="/assets/history-of-unix.svg" style="float: center;">

<br/>

## Licenses

You're looking at someone's code, when you see this weird "LICENSE" file...

[github.com/nims11/IPod-Shuffle-4g](https://github.com/nims11/IPod-Shuffle-4g)

Or, you've created a repo on github and seen the "Choose a license" option.

## Free vs. Open Source

### Free Software

Richard Stallman (developer of GNU software and founder of the Free Software
Foundation)
    - if you used gcc for 61c or the "ls" and "cd" commands, you used this
      man's stuff.

He's a bit...quirky. Here is his website:
[stallman.org](https://stallman.org/)

Free software allows its user to...

0. Run the software
1. Change the software
1. Redistribute the software
1. Redistribute the software with changes

[Free Software, Free Society TED Talk](https://www.youtube.com/watch?v=Ag1AKIl_2GM)

To promote this idea, the GPL license was created.

## GNU General Public License (GPL)

> **"Viral" license**: copyleft licenses are sometimes called "viral" licenses.
> This is because any derivative works must also be free software, so the
> copyleft license spreads like a virus. This can discourage people from using
> your projects in their own, possibly sabotaging the impact of your work.

> **"You"**: an avid copyleft advocate, also sometimes called "annoying to be
> around" and "probably suuuuper fun at parties".

What if I don't care about all this copyleft stuff and what people do with my code?

## MIT License

>MIT License
>
>Copyright (c) [year] [fullname]
>
>Permission is hereby granted, free of charge, to any person obtaining a copy
>of this software and associated documentation files (the "Software"), to deal
>in the Software without restriction, including without limitation the rights
>to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
>copies of the Software, and to permit persons to whom the Software is
>furnished to do so, subject to the following conditions:
>
>The above copyright notice and this permission notice shall be included in all
>copies or substantial portions of the Software.
>
>THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
>IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
>FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
>AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
>LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
>OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
>SOFTWARE.

True freedom. Live, laugh, kumbaya.

> **"Cuck" license**: permissive licenses are sometimes called "cuck" licenses—
> because you risk a big company taking what you made and making it
> proprietary. They'll bottle your water on AWS and sell it right back to your
> friends, family, and waifu. You cuck.

[hacker news post w/ gentoo wiki article](https://news.ycombinator.com/item?id=37383680)

## What about BSD and other licenses?

Not enough time. But check out [choosealicense.com](https://choosealicense.com)
if you're confused or want more options.

## Jaysa, why should I bother with all this license stuff? I just wanna make cool things.

I claim that you are broke in multiple ways.

P.S. If this isn't true, hop on over to [ocf.io/donate](ocf.io/donate) and give us all of your money pretty please 👉👈

## 1 - You are too broke to have a company rip off your personal projects that you poured your blood, sweat, and tears into.

[See the case of the creator of MINIX and Intel's IME chip.](https://www.techpowerup.com/238677/minix-creator-andrew-tanenbaum-sends-open-letter-to-intel-over-minix-drama)


## 2 - You are too broke to get fired or sued right now.

Still getting figured out this year:

> "Modern smart TVs come with software that tracks viewing habits to deliver
> targeted advertising directly on the TV screen. Software Freedom Conservancy
> purchased a Vizio TV to develop an open-source version of the operating
> system that was more customizable and didn't track users to show them ads.
> This Vizio TV runs on Linux, an operating system that legally requires
> manufacturers to share the code that lets users customize their devices. When
> SFC asked Vizio to provide the complete, corresponding source code (“CCS”),
> they refused. SFC sued Vizio in the Orange County Superior Court to receive
> this essential information." - [Software Freedom Conservancy](https://sfconservancy.org/copyleft-compliance/vizio.html)


So, let's come back to our ipod shuffle python script.

[github.com/nims11/IPod-Shuffle-4g](https://github.com/nims11/IPod-Shuffle-4g)

## Examples

### Situation 1

I use this script in a plugin I create for ncmpcpp, a terminal-based music
player. I distribute it under GPLv3, a newer GPL license, instead of GPLv2.

**WE ARE GNU + OK!!!**
<img src="/assets/happy-feet.jpg" style="float: center;">

> "This program is free software; you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by the
    Free Software Foundation; either version 2 of the License, or (at your
    option) any later version." - [GPL 2.0](https://www.gnu.org/licenses/old-licenses/gpl-2.0.txt)

### Situation 1 Part 2

I'm feeling nostalgic... I switch the license to GPLv1 instead because they
just don't make them like they used to.

**WE ARE GOING TO JAIL!!!**
<img src="/assets/go-to-jail.jpg" style="float: center;">

I use this script in a plugin I create for ncmpcpp, a terminal-based music
player. I distribute it with the GPLv3 instead of GPLv2.

### Situation 2

I fork the ipod-shuffle-4g repo and modify it so that it works for earlier
versions of the ipod shuffle, too. I publish the code on github and forget to
include a license at all.

**WE ARE GOING BACK TO JAIL!!!**
<img src="/assets/go-to-jail.jpg" style="float: center;">

I distributed a modified version of the code (by making it publicly available)
without it being under a GPL-compatible license. Copyleft/"Viral" nature of the
license comes into play here.

### Situation 3

I create a piece of software under the MIT license with publicly available
source code. However, I need some money, and no one's sponsoring me because it
turns out my code is allegedly "less crucial to infrastructure than the Linux
kernel".

So, I create a private fork which contains extra features and only give
access to people who sponsor the project.

**WE ARE SPONSORWARE!!!**
<img src="/assets/happy-feet-sponsorware.jpg" style="float: center;">

Proprietary, since users would only have freedom #1.

[See mkdocs material's license](https://squidfunk.github.io/mkdocs-material/insiders/license/#fair-use-policy)

[Also see the *open-core* model](https://en.wikipedia.org/wiki/Open-core_model)

### Situation 4

I create some cool database software under the AGPL license.

> “The GNU Affero General Public License [...] requires the operator of a
> network server to provide the source code of the modified version running
> there to the users of that server. Therefore, public use of a modified
> version, on a publicly accessible server, gives the public access to the
> source code of the modified version.”

My software is great and people love it! But big tech companies find a loophole. Someone in a consulting club graduates and comes up with a great idea for Amazon/Google Cloud/Azure: host my software on their platform and charge for it. I've been screwed over by SaaS - software as a service.

**WE ARE MONGODB!!!**
<img src="/assets/happy-feet-mongodb.jpg" style="float: center;">

This is why the Server Side Public License (SSPL) was then created. Under SSPL, cloud providers would have to open source the software and APIs the user needs to run an instance of MongoDB themselves.

[www.mongodb.com/legal/licensing/server-side-public-license](https://www.mongodb.com/legal/licensing/server-side-public-license)

If all of this interests you, look into the field of software & data privacy law!
