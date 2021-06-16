---
layout: post
title:  "Code navigation in Vim"
date:   2020-11-26 20:52:33 +0700
categories: blog
---

# Code navigation in Vim

Learn to navigate the code efficiently is a crucial part of being a developer. Before I use Vim, I'm was panic whenever someone approaches my computer and watch me write the code, even when it was a pair programming session. The most painful part is code navigation. it took me a while to navigate to the position I want to edit the code, searching things, find and replace. After all, I still can perform all those actions, but it was painful and unconfident.

Then I learn to use Vim.

## The most obvious way

The most obvious way to navigate is using the mouse, or `j` `k` to navigate up/down. It even worse when I use arrow keys to mo up/down sometimes. This is not efficient, let's avoid this.

## Jumping by line number

By showing the relative number, I now easier move to the line I want, e.g., 

- Move up 10 lines: `10k`
- Move down 15 lines `15j`

Then jump to the expected work by `f` and `t`, jump backward by `F` and `T`. For example, assume the cursor is at the beginning of this line, I want to jump to the second character `j` I press `fj;`

It still not so efficient, but I'm good with it for a year.

## Jumping by `incsearch`

Jumping by line number is still painful. I have to look at the line number and perform the jump, it is distracting.

```
set incsearch
set cursorline
```

## Combine them all

So far, jumping by `incsearch` is the most efficient way to navigate. I use it every day and feel better every day. Now I'm code with confidence even when the whole team watches my coding. 

But I'm not strict to any of the methods above. I use it all.
