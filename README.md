# st-grav
a fork of st (suckless terminal) perfected for my liking.

I wanted st to have the cool patches without having the unneccessary patches to keep it being as lightweight as it can

### [st v0.8.5](https://st.suckless.org/)

Fonts : [Hack](https://github.com/source-foundry/Hack), [Font Awesome v4 Compatibility](https://fontawesome.com/)

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
# for theme ease of use
cp yourtheme ~/.yourtheme
```
##### Open and reload xresources themes (put it something like .bashrc)
```bash
alias open="xrdb merge $1"
alias reload="kill -USR1 $(pidof st)"
# or both at the same time
function load { xrdb merge "$1" && kill -USR1 $(pidof st) }; export load
```
### Live reload demonstration
![demo](https://media1.tenor.com/images/3626897a0e57162257785622b8a3e61e/tenor.gif?itemid=26772972)
### Screenshots 

![full](https://i.postimg.cc/dLKc9sFb/full.png)

![float](https://i.postimg.cc/0Ns9Yf2z/single.png)

![multi](https://i.postimg.cc/wTnqvzCc/multi.png)

#### credits
- [siduck](https://github.com/siduck/st) (i basically ripped a majority of the ideas from them)
- [suckless](st.suckless.org) (for being cool)
