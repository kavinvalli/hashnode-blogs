## My Developer Setup in 2022!

I'm very excited for this article because I'm going to show you guys my developer setup! So, my developer setup is something which has evolved in the past few years. I've switched through editors, IDEs, browsers, etc. and this is what I use now. This might change in a few days/months/years too... who knows!

## Hardware
[M1 Macbook Air 2020](https://www.apple.com/in/macbook-air/) with 256GB storage and 8GB RAM with an external 27-inch monitor.

## Editor
The editor I generally use is [Neovim](https://neovim.io/). So, most of you would have heard of [Vim](https://www.vim.org/). Neovim started as a fork of Vim and has some really good features over vim. Recently, Neovim also released support for Native Language Servers.
The reason I use Neovim over editors like, VS Code and Sublime Text is primarily cause of the speed. This includes, speed of Neovim as an editor, comprising of startup time, less lagging, etc, and that also includes my speed as a developer. Vim might seem pretty daunting when you start with it, but when you get the hang of it, you'd want to use it everywhere. And I'm a big keyboard-only fan. So, the fact that I don't have to touch my mouse while writing code is a big plus point.

However, I do use [Visual Studio Code](https://code.visualstudio.com/) when collaborating with others in real time using the [Live Share extension](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare). And guess what! I use vim keybindings inside VSCode as well using the [Vim extension](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim).

Though, Neovim does have a few minus points to it
- You'll have to learn vim
- You'll have to spend some time customising neovim to suit your needs, and setup plugins for autocomplete, LSPs etc.

If you're a beginner, I highly recommend starting with VSCode and maybe use the vim extension if you want to start learning vim.

## Terminal Setup
I am a person, who's always on my terminal, especially cause of the fact that I use neovim as my primary code editor. I use [iTerm2](https://iterm2.com/) but I've heard of [Kitty](https://sw.kovidgoyal.net/kitty/) and [Alacritty](https://alacritty.org/) as pretty good alternatives.

I also use [tmux](https://github.com/tmux/tmux) heavily in my workflow. I use multiple tmux sessions for every project and recommend a lot of people to use it.

I use the [fish shell](https://fishshell.com/). It has some great features which you can find on the website which lead me to use it over zsh and bash.

I use [GNU Stow](https://www.gnu.org/software/stow/) to manage my configurations.

You can find my dotfiles in the repo linked below.


%[https://github.com/kavinvalli/dotfiles]

So that's it for this post. I might post an article specific to my Neovim Configuration and how I manage my dotfiles in the recent future.