---
layout: post
title:  "Terminal multiplexor minimal turorial"
categories: [blog, travel]
tags: [hot, summer]
d3: True
---

# tmux

several panes in one terminal window

sessions
* when ssh is disconnected session will keep
* sessions for different tasks
* connect to the shell of different user
*

## installation

`sudo apt-get install tmux`

`tmux`

*PREFIX KEY* + *COMMAND KEY*

C-  = Ctrl-

Panes

C-b  + %   =  split left/right
C-b  + "   =  split up / down

C-b + left/right  = go to prev/next pane

exit  or C-d  = close pane

Windows

C-b c  = new window

C-b + p/n  = go to prev/next window
C-b + <number> = go to window <number>

Sessions

C-b d   = detach session

tmux ls  = list of sessions
tmux attach -t 0  = attach to session 0
tmux new -s database = create session named "database"

## minimal usage

## usecases

## configs

Mouse control

```
# Enable mouse control (clickable windows, panes, resizable panes)
set -g mouse-select-window on
set -g mouse-select-pane on
set -g mouse-resize-pane on

# Enable mouse mode (tmux 2.1 and above)
set -g mouse on
```


## hotkeys