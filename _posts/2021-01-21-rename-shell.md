---
layout: post
title:  "Renaming shell's title in Ubuntu"
author: shiva
categories: [ Linux, Bash, Tools ]
image: assets/images/2021-01-21-rename-shell.gif
---
# How to rename shel's title in ubuntu

When you are working in a terminal environment, sometimes you need to open multiple
terminal applications. While you can handle it via Tmux or Screen, or in GUI envi
add the following lines in your `bash.rc`

```bash
function set-title(){
  if [[ -z "$ORIG" ]]; then
    ORIG=$PS1
  fi
  TITLE="\[\e]2;$*\a\]"
  PS1=${ORIG}${TITLE}
}
```

Then with the following command you can set a title:

```bash
$ set-title "My Project"
```

or

```bash
$ set-title "My shell :D"
```
