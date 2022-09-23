# st-grav
a fork of st (suckless terminal) perfected for my liking.

I wanted st to have the cool patches without having the unneccessary patches to keep it being as lightweight as it can

### [st v0.8.5](https://st.suckless.org/)

Fonts (Required for my Theme) : [Hack](https://github.com/source-foundry/Hack), [Nerd Fonts](https://github.com/ryanoasis/nerd-fonts) [~~Font Awesome v4 Compatibility~~](https://fontawesome.com/)

## [Patches](https://st.suckless.org/patches/) (Might remove some patches):
- boxdraw (st-boxdraw_v2-0.8.5.diff)
- alpha (st-alpha-20220206-0.8.5) [Needs a compositor]
- anysize (st-anysize-20220718-baa9357)
- font2 (st-font2-0.8.5)
- scrollback  (st-scrollback-0.8.5)
- sync  (st-appsync-20200618-b27a383)
- x resources live reload (st-xresources-signal-reloading-20220407-ef05519.diff)

### Installation (assumes you have git and base-devel)
```bash
git clone https://github.com/GravityShark0/st-grav/
cd ~/st-grav
make install
# for ease of use
cp /themes/yourtheme ~/.yourtheme
```
##### Open and reload xresources themes (put it something like .bashrc)
```bash
alias open="xrdb merge $1"
alias reload="kill -USR1 $(pidof st)"
# or both at the same time
function load { xrdb merge "$1" && kill -USR1 $(pidof st) }; export load

$ open yourtheme && reload
$ load yourtheme
```
###### if you are for some reason is using fish shell (you can type this manually)
```fish
alias open="xrdb merge"
alias reload="pidof st | xargs kill -s USR1"
# for both
function load0 -e load1
    xrdb merge $argv && pidof st | xargs kill -s USR1
end
alias load="emit load"
# saves aliases so you dont have to type it again
funcsave open reload load0 load

> open yourtheme && reload
> load yourtheme
```
### Live reload demonstration
![demo](https://media1.tenor.com/images/3626897a0e57162257785622b8a3e61e/tenor.gif?itemid=26772972)
### Screenshots 

![full](https://i.postimg.cc/hPX4cv5t/full.png)

![float](https://i.postimg.cc/0Ns9Yf2z/single.png)

![multi](https://i.postimg.cc/wTnqvzCc/multi.png)

### Keybindings (mostly default)
```
TERMMOD = Ctrl + Shift

Shift + Page Up   Scroll Up
Shift + Page Down Scroll Down
TERMMOD + C       Copy to Clipboard
TERMMOD + V       Paste from Clipboard
TERMMOD + Up      Font Size Increase
TERMMOD + Down    Font Size Decrease
```
#### credits
- [siduck](https://github.com/siduck/st) (i basically ripped a majority of the ideas from them)
- [suckless](st.suckless.org) (for being cool)
