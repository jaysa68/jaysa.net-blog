---
date:
    created: 2025-10-20
categories:
    - Tech
---

# Yubikey Configuration

<!-- more -->

Some services a yubikey is good for:

- SSH from any host (i.e. accessing my homelab server `kyu` from a random computer)
- Github (Passkey and/or 2FA)
- Discord (2FA)
- UC Berkeley account (2FA)
- Bitwarden (2FA)

## Naming

I add a small stickers to my yubikeys and name the corresponding SSH key / passkey / anything else, whenever possible and prompted, after that sticker.

## SSH

`HOST` is the host you want to log into.

`USER` is your username on the host you want to log into.

Run this command from any machine where you can plug in your yubikey:

`cat ~/.ssh/YOUR_YUBIKEY_NAME.pub | ssh USER@HOST "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"`

### FIDO2 SSH Key

Generate an SSH key on the yubikey: `ssh-keygen -t ed25519-sk -O resident -C "your_email@example.com"`. I skip the password. I do set a name (see *Naming* above). For an explanation of each part of the command, see the page below:

[dev.yubico: Securing SSH Authentication with FIDO2 Security Keys](https://developers.yubico.com/SSH/Securing_SSH_with_FIDO2.html)

I do not include `-O verify-required` because I don't want to be prompted for the pin all the time. For more information on User Verification, check this page:

[dev.yubico: User Presence vs User Verification](https://developers.yubico.com/WebAuthn/WebAuthn_Developer_Guide/User_Presence_vs_User_Verification.html)

### Loading SSH key on new hosts

Run `ssh-keygen -K`.

[dev.yubico: Securing SSH Authentication with FIDO2 Security Keys](https://developers.yubico.com/SSH/Securing_SSH_with_FIDO2.html)

Then, run a command similar to this:

`ssh -i ~/.ssh/jaysa_yubikey.pub jaysa@jaysa.net`

!!! info "Common SSH errors"

    To debug why SSH isn't working, run `ssh -vvv`. Here are some common reasons why:
    1. Using an alias for the hostname not present on your local host
    1. Not specifying your username for the remote host
    1. Didn't specify an identity file (the `-i` arg)
    1. Use the wrong path for the identity file.
         - Generated the ssh key in a place besides `.ssh`

Your SSH key pair is pretty useless without your yubikey plugged in, but you can delete it off the host once you're done if you want to be cautious.

## Github

### Setting a Pin

If you try to register your yubikey with certain services without setting a pin, it will error. For example, on Github, you may see the following:

> Passkey registration failed. This cannot be used as a passkey.

Below are the steps to set the pin.

1. Install and Open YubiKey Manager
    - On NixOS: `nix-shell -p yubioath-flutter`
    - Then, run `yubioath-flutter` to open the GUI.

2. Navigate to Passkeys -> Change Pin and set the pin.

## Discord

User Settings (bottom left corner gear icon) -> My Account -> Register a Security Key

## Password Manager Problems

Sometimes, I try to directly store a passkey in my password manager vault (Bitwarden) for some service, but it keeps prompting for my yubikey instead. In this case, check your excluded domains on your password manager. On Bitwarden, you can open the app or website and go to Settings -> Notifications -> Excluded Domains.
