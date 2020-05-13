---
title: Melhorando o Shell Script do Github
layout: post
tags: [linux, github, shellscript, bash, automação]
---
Para melhorar o shellscript do github que eu [criei](https://pellibr.github.io/learning-blog/2020/03/20/configurando-um-shell-script-para-atualizar-o-git-no-jekyll.html): 

1. [Aprender a criar condicionais no Shell Script].(https://tecadmin.net/tutorial/bash-scripting/bash-if-else-statement/)

2. [Aprender a criar argumentos para seu script.](https://tecadmin.net/tutorial/bash-scripting/bash-command-arguments/)

3. Criar Script para deploy no Heroku junto com o upgrade do Github. 

4. A ideia é usar no modo mais "fácil" sem usar nenhum argumento, ele irá adicionar todas as files no github e fazer o push para master e depois para o Heroku. 

5. Caso você queira adicionar um comentário, irá fazer a mesma coisa mas com o comentário criado no seu argumento. 

```
#!/bin/bash
if [ $# -eq 0 ]
	then
		git add .                           # track all files
		git add -u                          # track deletes
		git commit -m "generic"             # commit with message
		git push origin master              # push to origin
		git push heroku master 				# git push heroku master
	else
		git add .                           # track all files
		git add -u                          # track deletes
		git commit -m "$1" 		            # commit with message with argument
		git push origin master              # push to origin
		git push heroku master 				# git push heroku master
fi
```