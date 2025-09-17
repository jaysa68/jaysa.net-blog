---
title: Core Shell & Bash Scripting
date: 2025-09-16
---

# Core Shell & Bash Scripting

Presented to you by the
<img src="/assets/ocf-box.png" style="width:200px;float:center;margin:10px;">

and jaysa :)

<img src="/assets/bash-cover.png" style="float: center;">

<!-- more -->

# Getting Faster With Vim

Hopefully, you are now comfortable editing a file in vim, but you're probably still pretty slow. Don't worry! As you commit new commands to muscle memory, you will become faster.

If you're really dedicated to learning, try to learn a new command each day. Use that command whenever you get the chance until it feels natural.

The more commands that you know, the cooler you'll look to the guy behind you while you're taking notes in class.

<img src="/assets/nerd-cat.png">

^^ you programming with vscode

<img src="/assets/hacker-cat.png">

^^ you if you used vim instead



If you're stuck on which commands to learn next, check out the [Learn Vim Progressively](https://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/) article. It outlines a reasonable order to learn new vim tricks.

I'd prefer if you try to stick to vim while doing today's lab!

# Spotify Sucks

I wouldn't be standing here today if spotify didn't suck so hard, actually. I received a targeted podcast suggestion based on a youtube video I'd just watched, and for some reason, that triggered me to seek out how I could take back control from the large companies that make the software we basically need to exist now.

We're at UC Berkeley. So, I know that both you and I are too smart to have to put up with things like forced suggestions and shortcuts in the start menu of our desktop (that we even paid for!). Or to have our music taste, and overall media consumption, be determined by advertiser-driven algorithms.

I hope that the skills you learn in this class let you feel a bit more in-control of your devices and softare, like it did for me. Bash scripting is one of these skills, and a pretty fundamental one.

# Let's make an alternative...

So, after uninstalling spotify, I struggled to find a way to listen to music which approached Spotify's convenience. However... while cleaning my room back home awhile back, I stumbled across an old ipod shuffle from some distant Christmas.

I did some research on using ipod shuffles on linux (since I don't have any apple devices), and discovered the ipod-shuffle-4g python script that I showed you all last week. Let's try using it to upload music to my ipod.

Say I downloaded some mp3 file off of youtube onto my computer using one of those weird video-to-mp3 websites.

(dont @ me about piracy, I'm giving Red Leather way more money Thursday to see him live than the pennies Spotify would've given him for my listens)

<img src="/assets/first-script.png">

Who can tell me what happened as I ran each command?

Alright, we uploaded a single mp3 that we had to go manually download off of youtube onto my ipod. Not quite the level convenience we're looking for. Also, I already forgot that command we used.

## Bash Scripting

So, let's save that command in a script.

<img src="/assets/script-1.png">

Now, let's run that script.

<img src="/assets/script-2.png">

> Although `./` and `bash` do the same thing in this case, they are slightly different commands. `./` actually executes the file, whereas `bash` feeds the file as input into the bash interpreter. I would recommend `./` in most cases, so you can just execute without remembering the language of the script.

### Streams

Well, that's marginally better. What if I could specify the filepath to my script, instead of manually `cp`ing the file into the root directory of my ipod?

To do this, we need to take user input from the command line (aka `STDIN`, standard input).

[Gnu manual page on `read`](https://www.gnu.org/software/bash/manual/html_node/Bash-Builtins.html#index-read)

There are several other ways to manipulate streams of data in bash, for example:

1. Redirection: `echo "hello" > out.txt` to write hello to a new file `out.txt` in the cwd (current working directory).
2. Append: `echo "hello" >> out.txt` to append hello to `out.txt`
    - What's the difference between this and redirection?
3. Pipes: Take output of first command and "pipe" it into the second one, connecting stdin and stdout. `command1 | command2` 

### Variables

We're also going to need to store this somewhere. Let's do it in a variable called `song_name`

<img src="/assets/script-3.png">
<img src="/assets/script-4.png">

You can also store variables in a more basic way. For example:
```
FOO=1
OUTPUT=$((FOO+1))
echo $OUTPUT
```

will result in the terminal spitting back out `2`.

### Conditionals

Okay, now we can maybe take in the song name and later on feed it to the python script. Additionally, I'm now going to be using a cool music library tool called `beets` to keep track of all the songs on my laptop.

<img src="/assets/script-6.png">

<img src="/assets/script-5.png">

<img src="/assets/script-7.png">

<img src="/assets/script-8.png">

[Look at the GNU man page for more info on Bash Conditional Expressions](https://www.gnu.org/software/bash/manual/html_node/Bash-Conditional-Expressions.html)

A fancier example of if-else:
```
if [ “$1” -eq 79 ];
then
    echo “nice”
else
	echo “darn”
fi
```

Example using elif:
```
if [ “$1” -eq 79 ];
then
    echo “nice”
elif [ “$1” -eq 42 ];
then
    echo “the answer!”
else
	echo “wat r numbers”
fi

```

Example using case:
```
read -p "are you 21?" ANSWER
case "$ANSWER" in
  “yes”)
    echo "i give u cookie";;
  “no”)
    echo "thats illegal";;
  “are you?”)
    echo “lets not”;;
  *)
    echo "please answer"
esac
```

### Now draw the rest of the owl

Let's make some improvements to our script using what we've learned so far so we can download songs faster using `yt-dlp`, rather than doing it by hand.

<img src="/assets/rest-of-owl.jpg">
<img src="/assets/script-9.png">
<img src="/assets/script-10.png">

### Loops

I'll show you 2 kids of loops in bash: `for` and `while`.

#### For loop syntax

```
n=0
for x in {1..10}
do
	n=$(expr $x + $n)
done
echo $n
```

Running this would output `55`.

#### While loop syntax

```
while true
do
	echo "nightmare "
done
```

Running this would output `nightmare` until the user stops the program.

Let's use a `while` loop for our script:

<img src="/assets/script-11.png">

`<<<` is feeding the entire `song_path` variable, with all the song paths,

[stackoverflow post on how this while loop works](https://stackoverflow.com/questions/10929453/read-a-file-line-by-line-assigning-the-value-to-a-variable)

[stackoverflow post on <<<, the here string](https://unix.stackexchange.com/questions/80362/what-does-mean)

> I also use a dependency of the python script called `mutagen`, which I install temporarily with nix, so I can have playlists generated based on metadata. That is what the `-i` argument is there to indicate. We'll learn more about packages next week, and if you'd like to know more about nix, come talk to me :)


### Functions

I didn't use functions in today's example, but you may use them in today's lab, so here is a very basic one so you know the syntax:

```
function greet() {
    echo "hey there $1"
}
greet “sysadmin decal”

hey there sysadmin decal
```

### Tips

- bash syntax is weird af. spaces matter, read error messages carefully.
- as always, google your way to freedom
- ncmpcpp!!! terminal user interface (TUI) > graphical user interface (GUI)
    - tui tools exist for many things on linux, and are often faster + FOSS for more customizability!
    - plus, like vim, they make you look sososososo cool dude
