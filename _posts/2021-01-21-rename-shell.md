---
layout: post
title:  "Renaming shell's title in Ubuntu"
author: shiva
categories: [ Linux, Bash ]
image: assets/images/7.jpg
---
# How to rename shel's title in ubuntu
add the following lines in your bash.rc
```
function set-title(){
  if [[ -z "$ORIG" ]]; then
    ORIG=$PS1
  fi
  TITLE="\[\e]2;$*\a\]"
  PS1=${ORIG}${TITLE}
}

```
Then with the following command you can set a title:
```
set-title My Shell
or
set-title "My shell :D"
```
