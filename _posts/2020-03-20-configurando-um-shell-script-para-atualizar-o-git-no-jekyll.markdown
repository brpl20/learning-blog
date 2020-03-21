---
title: Configurando um Shell Script - Bash para Atualizar o Git no Jekyll
layout: post
tags: [jekyll, github, shellscript, bash, automação]
---

Em projetos mais simples de uso pessoal, como blogs de Jekyill por exemplo (duh) não há necessidade de versionamentos, branchs e gerenciamento de projetos... então para facilitar um pouco a nossa vida com os "gits" é melhor automatizar os comandos para evitar repetição de tarefas.

1. Criar um arquivo:
```
touch gitjek.sh
```

2. Edite o arquivo adicionando o código do Github:
```
#!/bin/bash
git add .                           # track all files
git add -u                          # track deletes
git commit -m "atualizacoes"        # commit with message
git push origin master              # push to origin
```

2. Os arquivos criados .sh não são executaveis automaticamente, então é preciso de uma autorização especial atraves do CHMOD. Você pode fazer o teste com um 'ls' antes de usar o chmod e depois do chmod para verificar que o arquivo mudou de cor, pelo menos nos terminais um pouco mais customizados, como oh my zsh.
```
chmod +x gitjek.sh
```

3. Agora basta executar o seguinte comando para as atualizações subirem direto no seu blog!
```
sh gitjek.sh
```

4. Caso queira também pode ser adicionado um comando para permitir ao usuário adicionar um comentário no commit através do comando
```
#!/bin/bash
read -r -p 'Commit message: ' desc  # prompt user for commit message
git add .                           # track all files
git add -u                          # track deletes
git commit -m "$desc"               # commit with message
git push origin master              # push to origin
```

5. Não se esqueça de adicionar o nome do arquivo no gitignore caso esteja usando a pasta raíz do repostiório.

## Resources
[tania](https://www.taniarascia.com/how-to-create-and-use-bash-scripts/)
