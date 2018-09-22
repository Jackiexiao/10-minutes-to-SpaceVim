# 十分钟Spacevim入门
[English version](https://github.com/Jackiexiao/10-minutes-to-SpaceVim/blob/master/README.md)

这篇文章的主要目的是让用户快速了解Spacevim，尝试Spacevim并不会删除你的原有vim
配置，如果你不喜欢Spacevim，你随时可以安全快速地切换回原来的配置。

只需要10分钟，来尝试一下吧。

## 目录
- [一、安装](#%E4%B8%80%E3%80%81%E5%AE%89%E8%A3%85)
- [二、基本概念](#%E4%BA%8C%E3%80%81%E5%9F%BA%E6%9C%AC%E6%A6%82%E5%BF%B5)
- [三、开始尝试](#%E4%B8%89%E3%80%81%E5%BC%80%E5%A7%8B%E5%B0%9D%E8%AF%95)
- [四、探索和自定义](#%E5%9B%9B%E3%80%81%E6%8E%A2%E7%B4%A2%E5%92%8C%E8%87%AA%E5%AE%9A%E4%B9%89)
- [参考](#%E5%8F%82%E8%80%83)

## 一、安装

**1. Install spacevim (Linux && macOS, for [windows](https://spacevim.org/quick-start-guide/#windows)),它不会删除你原有配置**

    curl -sLf https://spacevim.org/install.sh | bash

然后，开始尝试吧

    vim

第一次使用spacevim时，需要一些时间安装插件。

**2. 卸载并回滚到原vim**

    curl -sLf https://spacevim.org/install.sh | bash -s -- --uninstall

**3. 同时使用你原有的vim和spacevim**

See [FAQ:Have a try with SpaceVim without overwrite vimrc?](https://spacevim.org/faq/#have-a-try-with-spacevim-without-overwrite-vimrc)

**怎么进行安装的？**

其实只是重命名了你的`~/.vim`，名字改成`~/.vim_back`，用下面的命令查看安装脚本的更多信息
`curl -sLf https://spacevim.org/install.sh | bash -s -- -h`

**强烈建议:**

更新你的vim到
[vim8.0](http://tipsonubuntu.com/2016/09/13/vim-8-0-released-install-ubuntu-16-04/) 
或者 [neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim)
以便有更好的SpaceVim体验

## 二、基本概念
SpaceVim中有非常多的快捷键，最常用的快捷键是`空格键`，我猜这是为什么它叫spacevim。接下来
我们用简称`spc`来表示空格键。

### 1. 快捷键
有许多不同的快捷键，可以归为下面几类

| Prefix  | Prefix name | Example   | Description                     | More info                                                            |
| ------- | ----------- | --------- | ------------------------------- | -------------------------------------------------------------------- |
| `space` | `[SPC]`     | `spc f t` | open/close filetree             | just press space key and wait 1s                                     |
| `s`     | `[WIN]`     | `s v`     | split window, equal to `:split` | [link](https://spacevim.org/documentation/#window-manager)           |
| `\`     | `<Leader>`  | `\ [0-9]` | jump to other tab or buffer     | just press `\` key and wait 1s                                       |
| `g`     | go to       | `g 0`     | go to first tab                 | [link](https://spacevim.org/documentation/#commands-starting-with-g) |
| `z`     | fold        | `z a`     | toggle a fold                   | [link](https://spacevim.org/documentation/#commands-starting-with-z) |

进入spacevim后，按一下空格键，等待1秒，你可以看到有用的提示信息，通过这些
信息来浏览一下spacevim的更多快捷键吧。

### 2. 一些概念

| 名称 | 解释|
| --------- | ------------------------------------------------- |
| Window    | A window can split into more windows              |
| Buffer    | A buffer is a file loaded into memory for editing |
| Tab/Frame | A tab could contain different file                |
| Tagbar    | Display tags of current file                      |
| Filetree  | File browser                                      |

**对于vim新手**

如果你仍然不熟悉vim，可以在linux终端中输入`vimtutor`，进入vim的实战教程，大概
需要花半小时掌握vim的基本技能。

**对于vim的老用户**

SpaceVim 有些快捷键是和原生vim冲突的，例如`s` 和`g`，如果你想使用原生vim的配置，
在`~/.SpaceVim.d/init.toml`中加入

    [[options]]
    vimcompatible = true

更多vim兼容模式信息请查看
[vimCompatible mode](https://spacevim.org/documentation/#vim-compatible-mode)
特别是你只想更正其中的某个快捷键而保持其他不变。

SpaceVim默认使用`vimfiler`，你可能更喜欢用`nerdtree`，同样，
在`~/.SpaceVim.d/init.toml`中加入

    [[options]]
    filemanager = "nerdtree"


## 三、开始尝试

### 1. 最常用快捷键
虽然快捷键看起来很多，但是记起来并不麻烦，而且SpaceVim有很多提示，所以不要担心

留意：如果你使用了vim兼容模式（vimcompatible=true），下面的一些快捷键可能不生效

| Shortcuts        | Description                                                     |
| ---------------- | --------------------------------------------------------------- |
| 基本操作 |
| `h j k l`        | move around                                                     |
| `spc`            | wait 1 second to get hint for more shortcuts                    |
| `<F3> / spc f t` | trigger file tree                                               |
| `spc t t`        | Open tab manager                                                |
| `F2`             | Open tagbar                                                     |
| `<Leader> [1-9]` | switch to different tabs or buffers                             |
| `spc [1-9]`      | switch to different windows                                     |
| `ctrl j/h/k/l`   | switch to different windows                                     |
| 文件浏览器 | [Link](https://spacevim.org/documentation/#file-tree)           |
| `spc f o`        | open file tree and locate to current directory                  |
| `s g`            | open file and split window horizontally                         |
| `s v`            | open file split window vertically                               |
| 注释代码 | [Link](https://spacevim.org/documentation/#commenting)          |
| `spc c l`        | comment/uncomment current line                                  |
| `spc c p/P`      | comment/uncomment current paragraph                             |
| `spc ; [num] j`  | comment *num* lines                                             |
| 页面Tab管理器 | [Link](https://spacevim.org/documentation/#tabline)             |
| `spc t t`        | open tab manager                                                |
| `spc w F`        | open a new tab, equal to `spc t t + n`                          |
| `spc w o`        | switch tab                                                      |
| 显示相关 | [Link](https://spacevim.org/documentation/#ui-toggles)          |
| `spc s c`        | clear search highlight                                          |
| `SPC t 8`        | highlight any character past the 80th column                    |
| `SPC t h h`      | toggle highlight of the current line                            |
| `SPC t h c`      | toggle highlight indentation current column                     |
| 搜索 | [Link](https://spacevim.org/documentation/#searching)           |
| `spc s s`        | Searching in current file                                       |
| `spc s d`        | Searching in current directory                                  |
| `spc s b`        | Searching in all loaded buffers                                 |
| `spc s p`        | Searching in current proj, equal to `spc /`                     |
| 有用的快捷键 | [Link](https://spacevim.org/documentation/#unimpaired-bindings) |
| `[ spc`          | insert space above                                              |
| `] spc`          | insert space below                                              |

探索快捷键的最好方式依然是在spacevim中按下空格键等待一秒，它会弹出有用的提示框，
亲自尝试其中的快捷键才能更加准确知道它的效果。

### 2. 高级设置

#### (1) 特定编程语言支持
这里以python为例，其他语言可见[SpaceVim layers](https://spacevim.org/layers/#available-layers)

在`~/.SpaceVim.d/init.toml`中加入

    [[layers]]
	  name = "lang#python"

安装依赖

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


#### (2) 模糊搜索

模糊搜索是一个比较强大的功能，参见 [Fuzzy finder](https://spacevim.org/documentation/#fuzzy-finder). 

这里使用`unite`作为例子，在`~/.SpaceVim.d/init.toml`中加入

    [[layers]]
    name = "unite"

在终端中

    sudo apt-get install silversearcher-ag

对于linux用户，需要使终端的`ctrl-s`（停止屏幕变化）失效才能方便使用模糊搜索的功能。
在初始化脚本如(`~/.bashrc`) 中加入 `stty -ixon`

最后，开始使用模糊搜索，如模糊搜索当前文件夹下的文件

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



## 四、探索和自定义

### 1. 自定义
#### (1) Config `~/.SpaceVim.d/init.toml`

You may want to set `default_indent` to 4, edit `~/.SpaceVim.d/init.toml`

    [options]
    default_indent = 4

Actually it is  equivalent to set `~/.SpaceVim/autoload/SpaceVim.vim` to:

    let g:spacevim_default_indent = 4

Two way are the same except the second way need prefix `let g:spacevim_`

All SpaceVim options can be found in `:h SpaceVim-config` or the file `~/.SpaceVim/autoload/SpaceVim.vim`

#### (2) [Add your own vim script: bootstrap-functions](https://spacevim.org/documentation/#bootstrap-functions)

**举例说明如何使用`bootstrap-functions`**

if you want to `set wrap` (automatic line breaking) every time you open SpaceVim,
first, add a newfile `.SpaceVim.d/autoload/myspacevim.vim` which contains:

    func! myspacevim#before() abort
      set wrap
    endf

add below code to `~/.SpaceVim.d/init.toml`

    [options]
    bootstrap_before = "myspacevim#before"

Replace `before` to `after` if you want your function being called after the loading of SpaceVim’s main scripts

(OK, I know it's a bit inconvenient.)

#### (3) [Change your colorschemes](https://spacevim.org/documentation/#colorschemes)

### 2. 探索
1. Learn more about SpaceVim, please view [Official document](https://spacevim.org/documentation/)
2. Get more useful tool for your spacevim [Available layers](https://spacevim.org/layers/)
3. Check FAQ first if you have any problem [Frequently asked questions FAQ](https://spacevim.org/faq/)

### 3. 更多
1. 更新SpaceVim `:SPUpdate`
2. SpaceVim debug 信息`SPDebugInfo!` or `spc h I`, this is useful if you want 
to report bugs or open a github issue

## 参考
1. [Spacevim tutorial (writen in Chinese)](https://everettjf.gitbooks.io/spacevimtutorial/content/install/4.html)
2. [Hack-SpaceVim](https://github.com/Gabirel/Hack-SpaceVim)
