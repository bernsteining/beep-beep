# beep-beep

A list of tools to accelerate your workflow on a linux distro, favoring tools that run in TUI / CLI in order to run anything in a tmux pane, and to save RAM.

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

[zoxide](https://github.com/ajeetdsouza/zoxide): `cd` with teleportation.

[huniq](https://github.com/koraa/huniq): sort things uniquely.

[dust](https://github.com/bootandy/dust): check disk usage.

[difftastic](https://github.com/Wilfred/difftastic): diff that understands syntax.

[hexyl](https://github.com/sharkdp/hexyl): a hex viewer.

[xsel](https://github.com/kfish/xsel): pipe in your clipboard with `xsel -bi`.

[ptf](https://gitea.tfnux.org/adraenwan/ptf): share a file instantly over HTTP.

## windows manager & a bar

______________________________________________________________________

[Choose a windows manager that fits your needs](https://en.wikipedia.org/wiki/Comparison_of_X_window_managers)

Choose a status bar that fits your needs, [bumblebee-status](https://github.com/tobi-wan-kenobi/bumblebee-status) for example.

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

## type faster

______________________________________________________________________

[typing club](https://www.typingclub.com/): learn touch typing

learn the shortcuts:
![](hotkeys.png)

## terminal multiplexing

______________________________________________________________________

[screen](https://wiki.archlinux.org/title/GNU_Screen) or [tmux](https://github.com/tmux/tmux): keep a terminal session active in background, easily switch between your sessions, name them.

## pagers

______________________________________________________________________

[bat](https://github.com/sharkdp/bat): read code with colour syntax in your terminal.

[glow](https://github.com/charmbracelet/glow): read markdown in your terminal.

## JSON tools

______________________________________________________________________

[jq](https://github.com/stedolan/jq) / [yq](https://github.com/kislyuk/yq) / [xq](https://github.com/jeffbr13/xq): parse & switch between JSON / YAML / XLM seamlessly.

[rq](https://github.com/dflemstr/rq): parse switch & between JSON / protobuff / TOML / msgpack / \[...\] / seamlessly.

[fq](https://github.com/wader/fq): parse binary formats.

[gron](https://github.com/tomnomnom/gron): easily find the `jq` select syntax you're looking for.

## app launcher

______________________________________________________________________

[rofi](https://github.com/davatorium/rofi): fuzzy-find and launch your programs.

## markdown everything

______________________________________________________________________

[pandoc](https://github.com/jgm/pandoc): write markdown, generate PDF for your slides, or your thesis, fool everyone with LaTeX templates.

[hugo](https://gohugo.io/): write markdown and make a static site out of it for your blog.

[mdformat](https://github.com/executablebooks/mdformat): format your markdown.

## learn to use vim or emacs

______________________________________________________________________

Knowing how to use vim or emacs

add modules like [easymotion](https://github.com/easymotion/vim-easymotion)

## listen music

______________________________________________________________________

[spotifyd](https://github.com/Spotifyd/spotifyd): spotify deamon.

[spotify-tui](https://github.com/Rigellute/spotify-tui): spotify TUI client.

## screenshots & images workflow

______________________________________________________________________

[flameshot](https://github.com/flameshot-org/flameshot): screenshot any part of your screen and anotate it immediately.

[normcap](https://github.com/dynobo/normcap): screenshot any part of your screen and instantly OCR that part to your clipboard.

[viu](https://github.com/atanunq/viu): view images in your terminal.

[imagemagick](https://github.com/ImageMagick/ImageMagick): edit your pictures from the CLI.

## password management

______________________________________________________________________

[pass](https://www.passwordstore.org/): manage your password the UNIX way with gpg.

[rofi-pass](https://github.com/carnager/rofi-pass): fuzzy find your passwords and get them to your clipboard quickly.

## code related

______________________________________________________________________

[onefetch](https://github.com/o2sh/onefetch): quickly get stats & info about a `.git`.
[lazygit](https://github.com/jesseduffield/lazygit): TUI for `git`.

## manage multiple git identities

______________________________________________________________________

Never mix your git identities anymore

```
includeif.gitdir:~/perso/.path=.gitconfig-personal
includeif.gitdir:~/work/.path=.gitconfig-professional
```

with a .gitconfig:

```
[user]
	email = your_email
	name = your_identity
[core]
	editor = vim
```

Projects under perso/ will commit with your personal identity
Projects under work/ will commit with your professional identity

## manage your screen monitors

______________________________________________________________________

- [xrandr](https://wiki.archlinux.org/title/xrandr) (CLI)
- [arandr](https://github.com/chrysn/arandr) (GUI)

### todo

- add nvim modules
- emacs tips
- epub / pdf readers
