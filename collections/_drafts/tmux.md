---
layout: post
title:  "Terminal multiplexer minimal tutorial"
categories: [blog, travel]
tags: [hot, summer]
d3: False
---

`Terminal multiplexer` is a software that can multiplex several separate pseudoterminal-based login sessions inside one terminal. 

Main features:

1. **Persistence** - similar to `nohup`, permits to deconnect and reconnect without terminating runned processes
2. **Multiple windows** - split-sceens, several windows to have several terminals on one screen.
3. **Session sharing** - multiple users can connect to the same session.


Let's consider one popular **T**erminal **Mu**lteple**x**er - `tmux`. 

<!--more-->

## Installation

`sudo apt-get install tmux`

## Basic abstractions

* Session -
* Window -
* Pane -
* Config - 
* Control key - every control command will look like  `*PREFIX KEY* + *COMMAND KEY*` where `PREFIX KEY` is `Ctrl+B` by default. In this tutorial I will use `C-b` instead of `Ctrl+B`

## Basic functionalities

Here are some basic functionalities:

* when ssh is disconnected session will persist
* sessions for different tasks
* connect to the shell of different user


## Panes

`C-b`  + `%`   =  split left/right

`C-b`  + `"`  =  split up / down

`C-b` + `left/right`  = go to prev/next pane

`exit`  or `C-d`  = close pane

## Windows

`C-b` + `c`  = new window

`C-b` + `p/n`  = go to prev/next window

`C-b` + `<number>` = go to window `<number>`

## Sessions

`C-b` + `d`   = detach session

`tmux ls`  = list of sessions

`tmux attach -t 0`  = attach to session 0

`tmux new -s database` = create session named "database"


## Mouse control

```
# Enable mouse control (clickable windows, panes, resizable panes)
set -g mouse-select-window on
set -g mouse-select-pane on
set -g mouse-resize-pane on

# Enable mouse mode (tmux 2.1 and above)
set -g mouse on
```

## Usage optimized

Here we will discuss some configurations and best practicise to foster usage of tmux and make it more transparent and easier

## Links 

1. [tmux cheatsheet](https://gist.github.com/MohamedAlaa/2961058)
2. 
