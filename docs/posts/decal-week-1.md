---
title: Intro to Linux and FOSS
date: 2025-09-09
---

Presented to you by the
<img src="/assets/ocf-box.png" style="width:200px;float:center;margin:10px;">

<img src="/assets/linuxtm.png" style="float: center;">

<br/>

You're looking at someone's code, when you see this weird "LICENSE" file...

[github.com/nims11/IPod-Shuffle-4g](https://github.com/nims11/IPod-Shuffle-4g)

Or, you've created a repo on github and seen the "Choose a license" option.

## 

## Free vs. Open Source

### Free Software

Richard Stallman (developer of GNU software and founder of the Free Software Foundation)
    - if you used gcc for 61c, you used this man's stuff.

He's a bit...quirky. Here is his website:
[stallman.org](https://stallman.org/)

Free software allows its user to...

0. Run the software
1. Change the software
1. Redistribute the software
1. Redistribute the software with changes

[stallman.org](https://www.stallman.org/)

## GNU General Public License (GPL)

## Why should I care?

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
source code. However, I create a private fork which contains extra features and
only give access to people who sponsor the project.

**WE ARE SPONSORWARE!!!**
<img src="/assets/happy-feet.jpg" style="float: center;">

Proprietary, since users would only have freedom #1.

[See mkdocs material's license](https://squidfunk.github.io/mkdocs-material/insiders/license/#fair-use-policy)
[Also see the "open-core" model](https://en.wikipedia.org/wiki/Open-core_model)

### Situation 4

I first develop a piece of software under the AGPL license.

> “The GNU Affero General Public License [...] requires the operator of a
> network server to provide the source code of the modified version running
> there to the users of that server. Therefore, public use of a modified
> version, on a publicly accessible server, gives the public access to the
> source code of the modified version.”

I call this a Server Side Public License (SSPL).

**WE ARE MONGODB!!!**
<img src="/assets/happy-feet.jpg" style="float: center;">

[www.mongodb.com/legal/licensing/server-side-public-license](https://www.mongodb.com/legal/licensing/server-side-public-license)

If all of this interests you, look into the field of software & data privacy law!
