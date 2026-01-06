---
date:
    created: 2025-12-20
    updated: 2026-01-04
pinned: true
categories:
    - Tech
---

# December 2025 Homelab Overhaul

Senior year of college winter break project

<!-- more -->

New projects page to track hosts + services at [jaysa.net/homelab](https://jaysa.net/homelab).

1. Kyu (gaming pc, rgb ram)
    - my baby girl
1. Moxie (Thinkpad W540)
    - thrown out at a lab my ex-boyfriend used to do research at (same one from which I took kyu's CPU last year, a real messy off-and-on thing, thanks for asking)
2. Jewn (Dell Optiplex)
    - been sitting in OCF since my freshman year so i took her home. many of these sit in random campus buildings just chugging along

Make the laptop stay on when the lid closed:

`systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target`

[Source](https://forum.proxmox.com/threads/proxmox-gnome-workstation-howto-prevent-sleep-suspend.115580/)

## Preparation (01-04-2026)

I'm back in Turlock, so I'm using the old `kyu` on Arch Linux while I wait for Wednesday to arrive.

[https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/]

Gonna use cilium for CNI because it seems pretty common out there and I've heard of it before.

[https://docs.cilium.io/en/stable/installation/k8s-install-kubeadm/]

## FUTURE PLANS:
- check out Wireguard instead of Zerotier
- automate loading new music onto ipod shuffle whenever it is plugged into front-facing usb-a ports on `kyu`. currently done from my laptop, select new songs manually
- fairy lights plugged into the back of `kyu` should be on a timer, only come on after dark. perhaps shut off power to ports themselves?
