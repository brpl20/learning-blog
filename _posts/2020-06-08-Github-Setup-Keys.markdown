---
title: Criando e autenticando no Github com chaves de seguranca
layout: post
tags: [github, setup]
---

```
mkdir -p ~/.ssh && ssh-keygen -t ed25519 -o -a 100 -f ~/.ssh/id_ed25519 -C "TYPE_YOUR_EMAIL@HERE.com"
senha
cat ~/.ssh/id_ed25519.pub
github.com/settings/ssh
ssh -T git@github.com
```
