---
date:
    created: 2026-01-13
categories:
    - Gaming
    - Tech
---

# Steam Deck Modded Minecraft

A log of how I got it working.

![thumbnail](/assets/steamdeck-minecraft/thumbnail.png)

<!-- more -->

---

I already got emulation going for Super Mario Galaxy by following this [Retro Game Corps video](https://www.youtube.com/watch?v=89-LRCob6H8), and that wasn't too bad, so hopefully this won't be either.

Alright, starting with [this reddit comment](https://www.reddit.com/r/SteamDeck/comments/155otfh/comment/jsvjseo/). Didn't need to read past the first sentence. All I did was install Prism Launcher then [download the stuff I need for my modpack](http://blog.jaysa.net/2026/01/02/jaysacraft/#how-to-join).

![reddit comment](/assets/steamdeck-minecraft/reddit-post1.png)


## Bonus

While doing this, I got distracted installing the [Psion KDE Global Desktop Theme](https://store.kde.org/p/2138046) and got stuck because I forgot my root password, so I'm gonna reset it.

!!! note "How to Reset the Root Password"

    1. While the Steam Deck is powered off, hold the 3dots (QAM) and turn on the Steam Deck.
    
    1. The recovery menu will appear. On your keyboard highlight the 3rd option - CURRENT (OS Boot Menu) then press enter.
    
    1. The GRUB menu will appear. Highlight the 1st option - SteamOS then on your keyboard press "e" to edit the boot options.
    
    1. Press down cursor on the keyboard until steamenv_boot is highlighted. Press "end" to go to the end of the line.
    
    1. Enter the command - systemd.debug_shell
    
    1. Press CTRL-X to boot!
    
    1. Once SteamOS loads, press CTL-ALT-F9 on the keyboard to access the root debug shell.
    
    1. Enter the command - passwd deck
    
    1. Enter new password and retype the new password.
    
    1. Once done, press CTL-ALT-F1 on the keyboard to go back to game mode.
    
    [Instructions are from this other reddit post](https://old.reddit.com/r/SteamDeck/comments/16akwrf/steam_deck_tutorial_updated_reset_forgotten_sudo/).

I then put it in my password manager (Bitwarden) so I don't forget again.
