![](beep_beep.png)

# beep-beep

A list of tools to accelerate your workflow on a linux distro, with a focus on:

- ease of installation
- TUI / CLI
- RAM consumption

Table of contents:

1. [search & select & sort things](#search--select--sort-things)
1. [navigate](#navigate)
1. [windows manager & status bar & app launcher](#windows-manager--status-bar--app-launcher)
1. [terminal emulator](#terminal-emulator)
1. [terminal customization](#terminal-customization)
1. [terminal multiplexing](#terminal-multiplexing)
1. [network](#network)
1. [type faster & spell checking](#type-faster--spell-checking)
1. [pagers](#pagers)
1. [json everything](#json-everything)
1. [markdown everything](#markdown-everything)
1. [CLI IDE](#cli-ide)
1. [password management](#password-management)
1. [listen music](#listen-music)
1. [screenshots & images workflow](#screenshots--images-workflow)
1. [code related](#code-related)
1. [manage your screen monitors](#manage-your-screen-monitors)
1. [get documentation](#get-documentation)

## search & select & sort things

______________________________________________________________________

[fzf](https://github.com/junegunn/fzf): fuzzy-find in everything, especially your command history.

### Examples:

______________________________________________________________________

fuzzy select a running docker and jump in it.

```sh
function di(){docker exec -it "$(docker ps | fzf | cut -d' ' -f1)" /bin/sh}
```

fuzzy select a file, preview it with `bat` and open it with `nvim`.

```sh
function fz() {vim $(rg --files --hidden | fzf --preview "bat {}")}
```

fuzzy select an image while previewing it in the terminal and set it as your wallpaper.

```sh
function cwp() {feh --bg-scale --fullscreen $(rg --files ~/images/wallpapers/ | fzf --preview "termpix --width 100 --true-color {}")}
```

[ripgrep](https://github.com/BurntSushi/ripgrep): find patterns in files.

[fd](https://github.com/sharkdp/fd): find directories & files.

[dragon](https://github.com/mwh/dragon): drag & drop files to other apps from the term.

[procs](https://github.com/dalance/procs): `ps` with additional features.

[bottom](https://github.com/ClementTsang/bottom): `htop`-like for CPU, RAM, network with additional.

[huniq](https://github.com/koraa/huniq): sort things uniquely.

[delta](https://github.com/dandavison/delta): perfect files diffs.

[dust](https://github.com/bootandy/dust): check disk usage.

[difftastic](https://github.com/Wilfred/difftastic): diff that understands syntax.

[hexyl](https://github.com/sharkdp/hexyl): a hex viewer.

[xsel](https://github.com/kfish/xsel): pipe in your clipboard with `xsel -bi`.

[ptf](https://gitea.tfnux.org/adraenwan/ptf): share a file instantly over HTTP.

## navigate

[zoxide](https://github.com/ajeetdsouza/zoxide): `cd` with teleportation.

[broot](https://github.com/Canop/broot): navigate, get overviews of directories & never lose track of file hierarchy.

[vimfm](https://github.com/vifm/vifm): file manager with `vim` bindings.

[ranger](https://github.com/ranger/ranger): same as above.

[hunter](https://github.com/rabite0/hunter): not maintained anymore but still powerful.

## windows manager & status bar & app launcher

______________________________________________________________________

[Choose a windows manager that fits your needs](https://en.wikipedia.org/wiki/Comparison_of_X_window_managers)

Choose a status bar that fits your needs, [bumblebee-status](https://github.com/tobi-wan-kenobi/bumblebee-status) for example.

[rofi](https://github.com/davatorium/rofi): fuzzy-find and launch your programs.

## terminal emulator

______________________________________________________________________

[choose a terminal emulator that fits your needs](https://en.wikipedia.org/wiki/List_of_terminal_emulators)

## terminal customization

______________________________________________________________________

use [zsh](https://ohmyz.sh/) + [ohmyzsh](https://github.com/ohmyzsh/ohmyzsh)

add plugins in your `.zshrc`, for example:

```
plugins=(git zsh-completions zsh-syntax-highlighting zsh-autosuggestions
        colored-man-pages extract tmux ssh-agent)
```

## terminal multiplexing

______________________________________________________________________

[screen](https://wiki.archlinux.org/title/GNU_Screen) / [tmux](https://github.com/tmux/tmux) / [zellij](https://github.com/zellij-org/zellij)  / [byobu](https://www.byobu.org/): keep a terminal session active in background, easily switch between your sessions, name them.

## network

[nmtui](https://developer-old.gnome.org/NetworkManager/stable/nmtui.html): network manager TUI.

[termshark](https://github.com/gcla/termshark): Wireshark but in TUI.

[nload](https://linux.die.net/man/1/nload) & [bandwhich](https://github.com/imsnif/bandwhich): monitor bandwidth usage.

[rofi-bluetooth](https://github.com/nickclyde/rofi-bluetooth): manage & fuzzy-find bluetooth devices.

## type faster & spell checking

______________________________________________________________________

[typing club](https://www.typingclub.com/): learn touch typing

learn the shortcuts:
![](hotkeys.png#gh-light-mode-only)
![](white_hotkeys.png#gh-dark-mode-only)

[aspell](http://aspell.net/): spell check CLI.

## pagers

______________________________________________________________________

[bat](https://github.com/sharkdp/bat): read code with colour syntax in your terminal.

[glow](https://github.com/charmbracelet/glow): read markdown in your terminal.

## json everything

______________________________________________________________________

[jq](https://github.com/stedolan/jq) / [yq](https://github.com/kislyuk/yq) / [xq](https://github.com/jeffbr13/xq): parse & switch between JSON / YAML / XLM seamlessly.

[rq](https://github.com/dflemstr/rq): parse switch & between JSON / protobuff / TOML / msgpack / \[...\] / seamlessly.

[fq](https://github.com/wader/fq): parse binary formats.

[gron](https://github.com/tomnomnom/gron): easily find the `jq` select syntax you're looking for.

[fx](https://github.com/antonmedv/fx): interactive `.json` traversal & finder.

## markdown everything

______________________________________________________________________

[pandoc](https://github.com/jgm/pandoc): write markdown, generate PDF for your slides, or your thesis, fool everyone with LaTeX templates.

[hugo](https://gohugo.io/): write markdown and make a static site out of it for your blog.

[mdformat](https://github.com/executablebooks/mdformat): format your markdown.

## CLI IDE

______________________________________________________________________

learn how to use nvim or emacs

add modules like [easymotion](https://github.com/easymotion/vim-easymotion)

## password management

______________________________________________________________________

[pass](https://www.passwordstore.org/): manage your password the UNIX way with gpg.

[rofi-pass](https://github.com/carnager/rofi-pass): fuzzy find your passwords and get them to your clipboard quickly.

## listen music

______________________________________________________________________

[spotifyd](https://github.com/Spotifyd/spotifyd): spotify deamon.

```
# configure `spotifyd` to auth itself seamlessly with your `pass` password manager.
# ~/.config/spotifyd/spotifyd.conf
password_cmd = "pass show Web/spotifyd | head -n 1"
```

[spotify-tui](https://github.com/Rigellute/spotify-tui): spotify TUI client.

## screenshots & images workflow

______________________________________________________________________

[flameshot](https://github.com/flameshot-org/flameshot): screenshot any part of your screen and anotate it immediately.

[normcap](https://github.com/dynobo/normcap): screenshot any part of your screen and instantly OCR that part to your clipboard.

[viu](https://github.com/atanunq/viu): view images in your terminal.

[imagemagick](https://github.com/ImageMagick/ImageMagick): edit your pictures from the CLI.

## code related

______________________________________________________________________

[onefetch](https://github.com/o2sh/onefetch) & [tokei](https://github.com/XAMPPRocky/tokei): quickly get stats & info about a `.git` repo.

[gitui](https://github.com/extrawurst/gitui) & [lazygit](https://github.com/jesseduffield/lazygit): TUI for `git`.

[asdf](https://github.com/asdf-vm/asdf): manage multiple runtimes versions with one tool.

[hyperfine](https://github.com/sharkdp/hyperfine): benchmark any program.

[watchexec](https://github.com/watchexec/watchexec): watches a path and runs a command whenever it detects modifications.

[just](https://github.com/casey/just): better make.

[shellcheck](https://github.com/koalaman/shellcheck): warning & suggestions for shell scripts.

Never mix your git identities anymore

```
# ~/.gitconfig
[includeIf "gitdir:~/documents/prog/perso/"]
	path = .gitconfig-personal
[includeIf "gitdir:~/documents/prog/work/"]
  	path = .gitconfig-professional
```

```
# ~/.gitconfig-personal
[user]
	email = your_email
	name = your_identity
[core]
	editor = vim
```

code projects under:

- perso/\* will be committed with your `.gitconfig-personal` identity
- work/\* will be committed with your `.gitconfig-professional` identity

## manage your screen monitors

______________________________________________________________________

- [xrandr](https://wiki.archlinux.org/title/xrandr) (CLI)
- [arandr](https://github.com/chrysn/arandr) (GUI)

## get documentation

[tealdeer](https://github.com/dbrgn/tealdeer) & [navi](https://github.com/denisidoro/navi): common use cases of tools / cheatsheets instead of exhaustive man pages.

# more utils

[moreutils](https://joeyh.name/code/moreutils/)

### todo

- add nvim modules & conf tips & emacs tips
- epub / pdf readers
