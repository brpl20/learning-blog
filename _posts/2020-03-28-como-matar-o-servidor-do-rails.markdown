---
title: Como matar o servidor do rails
layout: post
tags: [rails]
---
Da mesma forma como matar processos no linux, usando o `lsof` para verificar os processos em aberto e `kill` para mata-los, mas como são muitos use desta forma para filtrar apenas os da porta 3000 (padrão rails):

`lsof -wni tcp:3000`

Depois:

`kill 32035`

32035 é o número do processo, alterar conforme o lsof.

Deve existir uma forma de fazer sem o lsof.


