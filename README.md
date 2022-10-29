# CPY64

A Commodore 64 editor written in Python.

![screen recording](https://user-images.githubusercontent.com/592709/199088866-52509f7c-ab4a-4064-bbfa-648766b1b04a.mp4)

## Features

* Direct and program mode
* C64 color palette
* 3 tone and 1 white noise generators
* PETSCII symbols and control characters
* Save and load programs
* C64 memory map with poke and peek
* Python and Scheme languages support

## Getting Started

### Terminal

1. Download and install *C64 TrueType Fonts* from https://style64.org/c64-truetype.
2. Change terminal font to *C64 Pro Mono*.
3. Use blinking block cursor with RGB color (112,109,235).

### Installation

    $ mkdir cpy64
    $ tar -xvf cpy64-xxx.cpython-yyy.tar.gz -C cpy64

    $ cd cpy64
    $ asdf install python yyy
    $ asdf local python yyy
    $ pip install --upgrade -r requirements.txt

### Usage

    $ cd cpy64
    $ python main.pyc   # up to a minute on the first start

## Keyboard Shortcuts

Key                                  | Action
------------------------------------ | --------------------------------------------
<kbd>↑</kbd>, <kbd>↓</kbd>         | Move the cursor up or down
<kbd>←</kbd>, <kbd>→</kbd>         | Move the cursor left or right
<kbd>HOME</kbd>                      | Clear the screen and return the cursor to the home position
<kbd>DEL</kbd>                       | Toggle the insert mode on or off
<kbd>CTRL-C</kbd>                    | Halt a running program
<kbd>CTRL-D</kbd>, <kbd>CTRL-Q</kbd> | Exit to shell
<kbd>ALT-1</kbd> to <kbd>ALT-8</kbd>    | Set color to black, white, red, cyan, purple, green, blue, and yellow correspondingly
<kbd>ALT-9</kbd>                     | Turn on reversed characters
<kbd>ALT-0</kbd>                     | Turn off reversed characters

## Commands

Command                                 | Action
--------------------------------------- | --------------------------------------------
CLR                                     | Clear the screen and return the cursor to the home position
LISP                                    | Set the current interpreter to Scheme
LIST [[\<first-line\>]-[\<last-line\>]] | Display all or part of the program in memory
LOAD "$"                                | List the programs in the *disk* directory
LOAD ["\<file-name\>"]                  | Load a program in the *disk* directory
NEW                                     | Clear the program and all variables
PYTHON                                  | Set the current interpreter to Python
RUN                                     | Start the program currently in memory
SAVE ["\<file-name\>"]                  | Save a program to the *disk* directory

## Memory Map

These memory values can be set or fetched with `POKE` and `PEEK`.

Location  | Label  | Description
--------- | ------ | --------------------------------------
212       | QTSW   | Flag: Editor in Quote Mode? 0=No
216       | INSRT  | Flag: Insert Mode 0=Off
1024-2023 |        | Video Matrix: 25 Lines by 40 Columns
36874     | SPKR1  | Speaker 1 – Music – Bass
36875     | SPKR2  | Speaker 2 – Music – Alto
36876     | SPKR3  | Speaker 3 – Music – Soprano
36877     | SPKR4  | Speaker 4 – Noise
36878     | VOLSET | Volume setting
53281     | BGCOL0 | Background Color 0: default color value is 7 (blue)
