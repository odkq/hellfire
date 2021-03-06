pabled
======
Pablo's own Editor

A small ncurses based console text editor with vi keybindings written in Python

This is a small editor I did with the intention of using it, it lacks
vi POSIX compatibility and lacks a lot of commands, but it is easier
to extend than others (at least for me)

Featuring:
 - Somehow vi-alike keybindings
 - Full UTF-8 support
 - Syntax highlighting using pygments for a whole lot of languages
 - A cool game (2048)
 - Hellfire!!

![2048](http://i.imgur.com/qxjJXSn.png)

![hellfire](http://i.imgur.com/JfvlU7n.png)

Requirements
------------

Requires Python 3.5, setuptools and pygments. To install on Debian Wheezy:

        apt-get install python3-pygments python3-setuptools

You will need also a terminal emulator and locale that support UTF-8, and a
font that can display Unicode graphic characters. As a reference, i use
'Bitstream Vera Sans Mono' in an xterm (xterm -fs 12 -fa 'Bitstream Vera Sans
Mono')

If you have a terminal that supports 256 colors, they will be used. But only
if you set the $TERM environment variable correctly. I do
export TERM=xterm-256color in xterm and TERM=screen-256color in tmux to get
256 colors.

Installation
------------
Install system-wide, with executable in /usr/local/bin/hellfire:

        sudo python3 ./setup.py install

Supported vi commands
---------------------
Command mode:

 - Motion commands:
  - k, j, h, l, +, -, cursor keys
  - Avpag, Repag, Control+f, Control+b
  - Home, End, 0 and $
 - Insertion:
  - a, i
 - Deletion:
  - x, X, Supr, Backspace, J, D, dd
 - Visual line selection:
  - V (start selection/end selection)
 - Copying:
  - (range)y or y over visual selection

Insert mode:

 - Motion commands
  - cursor keys, Home, End, Avpag

Ex (:) mode:
 - Substitution
  - s[ubstitute], using python regular expressions
 - Writing
  - w[rite] [file]

Unsupported vi features
-----------------------

There is no horizontal scroll...

You can not prefix a command with a repetition number (i.e. 10j)

Delete to end of line or to end of world (d$, dw) is not implemented

There is no undo (yet)

Games and other nuisances
-------------------------

 - Type :game2048 (or just :g) to play the popular game

 - Yup, type :hellfire to become the god of hellfire!

