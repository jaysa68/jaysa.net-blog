---
title: OCF Nix Decal Lecture
date:
    created: 2025-11-18
---

Presented to you by the
<img src="/assets/ocf-box.png" style="width:200px;float:center;margin:10px;">

and jaysa :)

<!-- more -->

<img src="/assets/decal-nix/cover.png" style="width:600px;">

## What is Nix?

First, Nix is a functional programming language. Nix is:

1. **domain-specific**: it is meant for creating nix derivations
1. **functional**: functions can be passed as args and returned as values
1. **pure**: the only result of a function is the value it returns; no side-effects.
1. **lazily evaluated**: expressions are not evaluated until the value is needed
1. **dynamically typed**: type-checking is done at runtime
1. **declarative**: think SQL. you state what the output should be, the computer decides what steps to execute to get there.
1. **reproducible**: same inputs to a nix program guarantees the same output

Tools heavily associated with nix are built using this language and reap those benefits. This includes NixOS and the Nix package manager, which we will cover more later on today.

## Basic Syntax

from [Zero to Nix](https://zero-to-nix.com/concepts/nix-language/) and the [nix.dev manual](https://nix.dev/reference/nix-manual.html)

I'll show my personal nix config for this laptop to illustrate.

### Strings

```
"Can be written like this"

''
  Or, they can be written
  Like this
    This line will be indented by 2 spaces in the final output.
  But the rest won't be indented at all!
''
```

New lines in the second form will persist in the final output.

### Lists

`my_list = [ 123 ./foo.nix "abc" (f { x = y; }) ]`

The final element of this list calls f on an attribute set? What is an attribute set, you ask...?

### Attribute Sets

Collections of name-value pairs.

```
{
  x = 123;
  text = "Hello";
  y = f { bla = 456; };
}
```

`{ a = "Foo"; b = "Bar"; }.a` evaluates to Foo.

```
let bar = "foo"; in
{ foo = 123; }.${bar}
```

Both evaluate to `123`.

### Functions

```
{
  my_value = my_function 2 3;
}
```

Calls a function on parameters 2 and 3, assigns output to `my_value`.

```
{
  my_function = x: y: x + y;
}
```

Defines `my_function`.

## NixOS

NixOS , like many other Linux distributions, is built around its package manager. But, machines running NixOS are configured using the Nix language. As a result, their configurations are fully **reproducible**.

Think about your current decal VM. If you wanted to replicate its state on another host exactly, how would you do it? Run all of the same commands and pray? What about if you hand-edited particular configuration files, such as `/etc/fstab`, when setting up the machine? Doing this imperatively is a big hassle that NixOS avoids

There are other tools, such as Terraform and Puppet, that try to solve this problem of declarative infrastructure, but do so a bit differently.

## Resources (CRUCIAL FOR TODAY'S LAB)

- [NixOS options](https://search.nixos.org/options?)
- [Nix pkg search](https://search.nixos.org/packages?)

## What else?

- Flakes
- Home Manager
    - [Home Manager options search](https://github.com/NixOS/nixfmt)
    - can use this to customize your OCF desktop setup! talk to me after lec for details
    - ongoing NixOS ricing competition ends soon...
    - [my OCF hyprland home manager config](https://github.com/jaysa68/hyprland-home-manager/blob/main/home.nix)
- devenv

## Tips

- To write good nix code, look at other people's good nix code!
    - The official [NixOS github](https://github.com/NixOS), for example. Or the [ocf/nix repo](https://github.com/ocf/nix) (marginally less good).
    - check out contributors to Nix projects and see if their configurations or dotfiles are public
- Be patient with Nix syntax. It'll give you a lot of errors at first, but you'll have less as you get better.
    - Additionally, take a look at [nixfmt](https://github.com/NixOS/nixfmt) for code formatting.
- Don't get too caught up in fully understanding Nix. You can still use it without knowing many of the theoretical nuances about what makes it so good just yet.

    - If you are interested, you can start with the [original Nix paper](https://edolstra.github.io/pubs/nspfssd-lisa2004-final.pdf), some guy's college thesis.
    - an ocf alumni also wrote his own doc on [How to learn Nix](https://bestdocs.ocf.io/staff-docs/nix/how-to-learn-nix/) you can check out
