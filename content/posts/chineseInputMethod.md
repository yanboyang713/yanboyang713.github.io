---
title: "Getting Started Fcitx with chinese input method in Linux"
date: 2021-12-06T13:56:00+08:00
tags: ["Fcitx", "chinese", "linux"]
categories: ["Linux"]
draft: false
---

## Introduction {#introduction}

Fcitx is a lightweight input method framework aimed at providing environment independent language support for Linux. It supports a lot of different languages and also provides many useful non-CJK features.

In this article, I will introduction:

1.  How to install Fcite in Manjaro/Arch Linux.
2.  How to Config Environmental variables


## Install fcite packages in Manjaro {#install-fcite-packages-in-manjaro}

```bash
yay -Syu adobe-source-han-sans-otc-fonts adobe-source-han-serif-otc-fonts
```

```bash
yay -Syu fcitx fcitx-googlepinyin fcitx-im fcitx-configtool
```


## Config Environmental variables {#config-environmental-variables}

```bash
vim ~/.profile
```

add:

```file
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx

fcitx &
```

```bash
source .profile
```
