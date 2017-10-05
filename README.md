# agnoster-bash
Agnoster Theme for Bash

agnoster's Theme - https://gist.github.com/3712874
A Powerline-inspired theme for BASH

(Converted from ZSH theme by Kenny Root)
https://gist.github.com/kruton/8345450

Updated & fixed by Hanish K H on oct-05-2017

# UPDATE
Fixed the virtualenv prompt in bash

# README

In order for this theme to render correctly, you will need a
[Powerline-patched font](https://gist.github.com/1595572).
I recommend: https://github.com/powerline/fonts.git
```
git clone https://github.com/powerline/fonts.git fonts
cd fonts
install.sh
```

In addition, I recommend the
[Solarized theme](https://github.com/altercation/solarized/) and, if you're
using it on Mac OS X, [iTerm 2](http://www.iterm2.com/) over Terminal.app -
it has significantly better color fidelity.

Install:

I recommend the following:
```
cd $HOME
mkdir -p .bash/themes/agnoster-bash
git clone https://github.com/speedenator/agnoster-bash.git .bash/themes/agnoster-bash
```

then add the following to your .bashrc:

```
export THEME=$HOME/.bash/themes/agnoster-bash/agnoster.bash
if [[ -f $THEME ]]; then
    export DEFAULT_USER=`whoami`
    source $THEME
fi
```

# Goals

The aim of this theme is to only show you *relevant* information. Like most
prompts, it will only show git information when in a git working directory.
However, it goes a step further: everything from the current user and
hostname to whether the last call exited with an error to whether background
jobs are running in this shell will all be displayed automatically when
appropriate.

Generally speaking, this script has limited support for right
prompts (ala powerlevel9k on zsh), but it's pretty problematic in Bash.
The general pattern is to write out the right prompt, hit \r, then
write the left. This is problematic for the following reasons:
- Doesn't properly resize dynamically when you resize the terminal
- Changes to the prompt (like clearing and re-typing, super common) deletes the prompt
- Getting the right alignment via columns / tput cols is pretty problematic (and is a bug in this version)
- Bash prompt escapes (like \h or \w) don't get interpolated

all in all, if you really, really want right-side prompts without a
ton of work, recommend going to zsh for now. If you know how to fix this,
would appreciate it!

![ScreenShot](agnoster-bash-sshot.png)
