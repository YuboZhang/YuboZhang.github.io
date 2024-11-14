---
title: How to config github proxy with http/https/ssh
date: 2024-11-14 13:37:06
updated: 2024-11-14 13:37:06
categories:
  - [Tool]
tags:
  - Linux
  - github
  - proxy
mathjax: false
---

## config proxy for http/https

```
git config --global http.proxy socks5://127.0.0.1:1080
git config --global https.proxy socks5://127.0.0.1:1080
```

or edit the file ~/.gitconfig and add the following item

```
[http]
      proxy = socks5://127.0.0.1:1080
[https]
      proxy = socks5://127.0.0.1:1080
```

## config proxy for ssh

### install proxychains

use the tool `proxychains`, run the following command to install in arch Linux based distributions (i.e. Manajaro).

```
sudo pacman -S proxychains-ng
```

### config proxychains

edit the file `/etc/proxychains.conf`, add a line in the `ProxyList` item

```
[ProxyList]
socks5 127.0.0.1 1080
```

### set up alias

Open the file `~/.zshrc` (in manjaro) and add the following line:

```
alias git="proxychains -q git"
```
Now you can use git commands by ssh if a public ssh-key has been shared to your account on `Github.com`.

