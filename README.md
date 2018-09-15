# 10 minutes to SpaceVim (for linux user)
The main purpose of this tutorial is quickly introducing spacevim to new 
beginners. Also, for old vimer, it won't hurt to try, you can easily and safely
get back to your original vim if you don't like spacevim.

Just need 10 minutes, have a try!!

## Table of Content
- [First Step: Install or Uninstall](#first-step-install-or-uninstall)
- [Second Step: Basic idea](#second-step-basic-idea)
- [Third Step: Getting start!](#third-step-getting-start)
- [Fourth Step: Explore and customize](#fourth-step-explore-and-customize)
- [Reference](#reference)

## First Step: Install or Uninstall

**1. Install spacevim (Linux && macOS), it won't delete your original vim.**

    curl -sLf https://spacevim.org/install.sh | bash

Then, get start!

    vim

The first time you type `vim`, it will take few minutes to install plugins.

**2. Uninstall spacevim and get back to your original vim!**

    curl -sLf https://spacevim.org/install.sh | bash -s -- --uninstall

**3. Use both of your original vim and spacevim**

See [FAQ:Have a try with SpaceVim without overwrite vimrc?](https://spacevim.org/faq/#have-a-try-with-spacevim-without-overwrite-vimrc)

**How it works?**

Actually it just change the name for `~/.vim` to `~/.vim_back`, for more 
information about install script, type
`curl -sLf https://spacevim.org/install.sh | bash -s -- -h`

**Suggestion:**

Update your vim to 
[vim8.0](http://tipsonubuntu.com/2016/09/13/vim-8-0-released-install-ubuntu-16-04/) 
or [neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim)
to get better experience of spacevim

## Second Step: Basic idea
There are many shortcuts key in SpaceVim, the most frequently used shortcut 
keys are often starting with `Space key`, I guess that's why we call it 
SpaceVim. For convenience, when we mention `spc`, it means the Space key on 
keyboard.

### 1. Shortcuts
There are different kinds of shortcuts, start with different prefix:

| Prefix | Prefix name | Example | Description | More info |
| ------ | ----------- | ------- | ----------- |-- |
| `space` | `[SPC]`     | `spc f t` | open/close filetree             | just click space key|
| `s`     | `[WIN]`     | `s v`     | split window, equal to `:split` |[link](https://spacevim.org/documentation/#window-manager) |
| `\`     | `<Leader>`  | `\ [0-9]` | jump to other tab or buffer     | just click `\` key|
| `g`     | go to      | `g 0`     | go to first tab                 |[link](https://spacevim.org/documentation/#commands-starting-with-g)|
| `z`     | fold | `z a` | toggle a fold | [link](https://spacevim.org/documentation/#commands-starting-with-z)

Just click the button `spc`, wait 1 second, you will see useful hint to shortcuts

### 2. Key Conceptions

| Name     | Description                                       |
| -------- | ------------------------------------------------- |
| Window   | A window can split into more windows              |
| Buffer   | A buffer is a file loaded into memory for editing |
| Tab      | A tab could contain different file                |
| Tagbar   | Display tags of current file                      |
| Filetree | File browser                                      |

**For new beginners to vim**

Still confusing about how to use vim? Type `vimtutor` in your terminal, it will
 open a vim tutorial, you just need half an hour to master basic skills of vim.

**For old vimer**

As you could see above, spacevim's shortcuts are confict with origin vim's 
shortcuts such as shortcuts start with `s` and `g`, if you want to use origin
vim key bindings, you can enable vimcompatible mode, add 

    [[options]]
    vimcompatible = true

to `.SpaceVim.d/init.toml`

Spacevim's default file tree plugin is `vimfiler`, for those who used to using
`nerdtree` plugin to explore file, set 

    [[options]]
		filemanager = "nerdtree"


## Third Step: Getting start!

### 1. The most frequently used shortcuts

Be carefully, if you use vim compatible mode, in vim normal mode, shortcuts 
blew starts with `s` and `q` won't work.

| Shortcuts        | Description                                            |
| ---------------- | ------------------------------------------------------ |
| Basic            |
| `h j k l`        | move around                                            |
| `spc`            | wait 1 second to get hint for more shortcuts           |
| `<F3> / spc f t` | trigger file tree                                      |
| `spc t t`        | Open tab manager                                       |
| `F2`             | Open tagbar                                            |
| `<Leader> [1-9]` | switch to different tabs or buffers                    |
| `spc [1-9]`      | switch to different windows                            |
| `ctrl j/h/k/l`   | switch to different windows                            |
| Filetree         | [Link](https://spacevim.org/documentation/#file-tree)  |
| `spc f o`        | open file tree and locate to current directory         |
| `s g`            | open file and split window horizontally                |
| `s v`            | open file split window vertically                      |
| Comment code     | [Link](https://spacevim.org/documentation/#commenting) |
| `spc c l`        | comment/uncomment current line                         |
| `spc c p/P`      | comment/uncomment current paragraph                    |
| `spc ; [num] j`  | comment *num* lines                                    |
| Tab Manager      | [Link](https://spacevim.org/documentation/#tabline)    |
| `spc t t`        | open tab manager                                       |
| `spc w F`        | open a new tab, equal to `spc t t + n`                 |
| `spc w o`        | switch tab                                             |
| Display          | [Link](https://spacevim.org/documentation/#ui-toggles) |
| `spc s c`        | clear search highlight                                 |
| `SPC t 8`        | highlight any character past the 80th column           |
| `SPC t h h`      | toggle highlight of the current line                   |
| `SPC t h c`      | toggle highlight indentation current column            |
| Search           | [Link](https://spacevim.org/documentation/#searching)  |
| `spc s s`        | Searching in current file                              |
| `spc s d`        | Searching in current directory                         |
| `spc s b`        | Searching in all loaded buffers                        |
| `spc s p`        | Searching in current proj, equal to `spc /`            |


### 2. Advanced shortcuts

#### (1) Programming language support
Use spacevim as a specific language IDE, take `python` for example.
for other programming language, please view [SpaceVim layers](https://spacevim.org/layers/#available-layers)

Add following snippet to `.SpaceVim.d/init.toml`

    [[layers]]
	  name = "lang#python"

Install dependencies

    pip install --user flake8 yapf autoflake isort

* flake8 : for syntax checking feature
* yapf : for formatting code
* autoflake : for uppress unused imports 
* isort : for sort your imports

| Shortcuts   | Description                            |
| ----------- | -------------------------------------- |
| `g d`       | Go to function definition              |
| `spc b f`   | format code according to pep8 standard |
| `spc l g d` | generate docstring                     |
| `spc l s i` | open ipython                           |
| `spc l r`   | run python code                        |


#### (2) Fuzzy finder

See [Fuzzy finder](https://spacevim.org/documentation/#fuzzy-finder). For example,
we use unite as a fuzzy finder, to enable it, add following snippet to 
`.SpaceVim.d/init.toml`

    [[layers]]
    name = "unite"

and in terminal

   sudo apt-get install silversearcher-ag

Then disable `ctrl-s` in linux terminal , stick `stty -ixon` in a startup script(`~/.bashrc`). 
To allow `ctrl-s` to get things flowing again, use `stty ixany`.

Finally, in spacevim

    spc f f

| Shortcuts            | Description                               |
| -------------------- | ----------------------------------------- |
| `<Tab> / Ctrl-j`     | Select next line                          |
| `Shift-Tab / Ctrl-k` | Select previous line                      |
| `j k`                | Leave Insert mode (Only for denite/unite) |
| `Ctrl-w`             | Delete backward path                      |
| `<Enter>`            | Run default action                        |
| `Ctrl-s`             | Open in a split                           |
| `Ctrl-v`             | Open in a vertical split                  |
| `Ctrl-t`             | Open in a new tab                         |
| `Ctrl-g`             | Exit unite                                |



## Fourth Step: Explore and customize

### 1. Customize
1. [Change your colorschemes](https://spacevim.org/documentation/#colorschemes)
2. [Add your own vim script: bootstrap-functions](https://spacevim.org/documentation/#bootstrap-functions)

### 2. Explore
1. Learn more about SpaceVim, please view [Official document](https://spacevim.org/documentation/)
2. Get more useful tool for your spacevim [Available layers](https://spacevim.org/layers/)
3. Check FAQ first if you have any problem [Frequently asked questions FAQ](https://spacevim.org/faq/)

### 3. More
1. Update SpaceVim `:SPUpdate`
2. SpaceVim debug info `SPDebugInfo!` or `spc h I`, this is useful if you want 
to report bugs or open a github issue

## Reference
1. [Spacevim tutorial (writen in Chinese)](https://everettjf.gitbooks.io/spacevimtutorial/content/install/4.html)
2. [Hack-SpaceVim](https://github.com/Gabirel/Hack-SpaceVim)
