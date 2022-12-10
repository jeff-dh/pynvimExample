# pynvimExample

This is the pynvim rplugin example I was looking for when I did my first steps with pynvim (and couldn't find anything similar). It is meant to be for demonstration / documentation purpose and should hopefully help others to get started with pynvim quickly.

It is supposed to be very basic and easy to understand and at the same time face common issues a real world nvim plugin faces.

This example plugin has the following properties:

- ~**100 lines of code**
- it's does something more or less useful (it can run a python scripts that's loaded in the curent vim buffer and shows the stdout output of it in a floating window)
- it's a **(packer) installable** plugin
- it can be **configured from within lua** init scripts like a "native" lua plugin (`requires('pynvimExample').setup{height=20}`)
- it can alternatively be **configured from a vim init script** (`let g:PynvimExample_height = 20`)
- it **creates a new buffer** and manipulates it
- it creates and shows a **floating window**
- it uses not wrapped **`nvim_*` api functions**
- it uses a **python callback** handler with parameters (this is a more or less homebrewed solution! I don't know whether that really makes sense or whether there are better solutions to achieve working python callbacks with pynvim)

I appreciate any feedback, ideas, opinions....

- what's missing?
- what else should be demonstrated to get started with pynvim?
- are there better solutions / designs (for example for the callback or configuration)?
- ....?

## Installation

packer:
```lua
 use({
    'jeff-dh/pynvimExample',
     run=':UpdateRemotePlugins'
 })
```

## Configuration

lua:
```lua
require('pynvimExample').setup({
    height = 20
    })
```
or

vim script (untested!)
```vim
let g:PynvimExample_height=20
```

## Usage

- open a simple python file you want to execute (it should contain some print statements)
- execute the command `:PynvimExampleRun`
- switch the focus to another window (for example back to the python file)

![](https://raw.githubusercontent.com/jeff-dh/pynvimExample/main/screenshot/pynvimExample.png)
