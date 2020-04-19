---
title: como abrir o rails s e seu browser ao mesmo tempo
layout: post
tags: [linux, rails, automação]
---
Dica básica e boba para economizar um tempo...

Se você estiver trabalhando com uma aplicação de Rails, fazendo muitos testes por exemplo, pode usar este comando para evitar ficar abrindo o navegador e digitando o localhost:3000 e navegando no seu aplicativo...

_localhost padrão_
`rails s & sleep 4 && firefox http://localhost:3000/`

_local host testando a create/new por exemplo_
`rails s & sleep 4 && firefox http://localhost:3000/clinets/new`

_firefox com private windows_
`rails s & sleep 4 && firefox -private-window http://localhost:3000/clinets/new`

--- 
# Update 19/04/2020

Esse método parece não ser muito bom uma vez que o servidor parece continuar mesmo depois do `ctrl+c` e causa conflito de continuar aberto mesmo depois de tentar fechar, obrigando a matar o servidor 'forçadamente'. 