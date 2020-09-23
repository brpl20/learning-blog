---
title: Git Force Pull
layout: post
tags: [Github]
---
Git force pull, quando você faz alterações e esqueceu de dar o pull, especialmente se forem alterações pequenas, que serão sobrescritas. 


```
git fetch origin master
git reset --hard FETCH_HEAD
git clean -df
```
