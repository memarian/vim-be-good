# vim-be-good
Vim be good is a plugin designed to make you better at vim by creating a game
to practice basic movements in.

## WARNING
* Read Installation instructions carefully.  There has been some confusion
  around that.
* The code is a heaping pile of awfulness.  It was developed live on Twitch,
  which means I did not carefully think through anything other than memes.
* If you are looking to extend it I am about to do a refactor in the next
  couple of weeks to improve the current codebase and make a simplier
  contributor model.

## Difficulty
The difficulty only works on a few games for now.

## Ideas?
Please submit a ticket for your idea!!!

## Options

By default vim be good uses a floating buffer.  If you wish to have it use the
current buffer (only if its empty) set `vim_be_good_floating` to 0.

`let g:vim_be_good_floating = 0`

## Instructions are at top of games.
here too!

To play `relative` you need to delete the line that
says `DELETE ME`.  Use relative jumps

To play `ci{` you need to replace the contents
inside the _first_ { or [ with bar.  HINT, use ci[
or ci{ and type bar.

To play `whackamole` you need to navigate to the character with the caret under
it as fast as possible. Once you have reached the character, flip the
character's case to complete the round.

## Installation

1. Use your favorite plugin manager to install!  Only works on Nvim, the one true
vim.
 
Linux
```viml
Plug 'ThePrimeagen/vim-be-good', {'do': './install.sh'}
```

Windows 10 - PowerShell
Requirements:
[Git for Windows BASH emulation](https://gitforwindows.org/)
[NodeJs](https://nodejs.org/en/download/)

```viml
Plug 'ThePrimeagen/vim-be-good', {'do': '.\install.sh'}
```

2. Then execute `:UpdateRemotePlugins` to finish the installation process.

If you run into any problems when running the `:UpdateRemotePlugins` run `:checkhealth` to check if your vim is node ready.

3. If healthcheck fails node ready you need to install neovim.
```
# I am sorry for the global install
npm install -g neovim
```

## Playing the games.
Before doing ANYTHING at all, make sure you are in an empty file.  If the file
you are in is not empty, VimBeGood will throw an error.

Ok, you are in an empty file, so first execute the following.

```viml
:VimBeGood
```

This will echo out the available set of games.  Each game can take a set of
options to change how it is played, the above help menu should include each game.

## Future Games
Please make an issue if you have a command you wish to practice and i'll make
it into game!!

## Live on Stream
Everything you see here has been developed on stream at [ThePrimeagen](https://twitch.tv/ThePrimeagen).
Stop by and troll away.  Helpful troll hints would be to complement the size of my hands.

## Issues
Please file an issue.  But if you do, please run the logger first and paste in
the input.

`NVIM_NODE_LOG_FILE=nvim.log nvim` -- this should print out all the
console.log's that come with vim-be-good.  And it should give ThePrimeagen an
idea of how to stop sucking

## Contribute
- Fork
- Create a feature branch
- Make changes
- Build `npm i && npm run build && nvim --headless -c ":UpdateRemotePlugins" -c ":qa"`
- Modify the configuration to use local build:
`~/.config/nvim/init.vim`
```
    call plug#begin('~/.vim/plugged')
    Plug '/tmp/vim-be-good' " path to your vim-be-good fork
    call plug#end()
```
- Check your new feature `NVIM_NODE_LOG_FILE=/tmp/nvim.log nvim +VimBeGood` (you can view logs with `less /tmp/nvim.log`)
- Make PR
