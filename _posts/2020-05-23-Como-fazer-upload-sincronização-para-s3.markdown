---
title: Como fazer upload e sincronização para a S3
layout: post
tags: [rails, devise]
---

1. Quando trabalhar com arquivos da S3 com arquivos locais, é interessante fazer um processo de sincronização com os seus arquivos da nuvem, como como /local com /s3:bucket, no me ucaso será o seguinte: 

```
Local: ~/aws_swap
Remote: S3:bucket
```

# Instale Configure o CLI do seu S3

Intale o AWS Command Line Interface na sua máquina e se familiarize com alguns comandos básicos, em termos gerais serão os mesmos comandos de uma máquina local mas específicos para o AWS, como por exemplo `aws s3 ls` para listar os seus buckets.

Também será preciso ajustar suas credenciais. 

Confira mais informações [aqui](https://docs.aws.amazon.com/pt_br/cli/latest/userguide/cli-chap-welcome.html).

# Ajuste as configurações desejadas: 

1. No meu caso, eu quero sincronizar todos os documentos de word, ou seja DOCX. É uma pasta específica deste tipo de documento, mas eu tenho alguns códigos em ruby ".rb" que eu desejo excluir. Eu só quero que as alterações salvas em minha máquina tenham efeito, ou seja, será uma sincronização unilateral e finalmente, eu quero que os arquivos excluídos da minha máquina também sejam excluídos da S3.

# Comandos 

1. A AWS CLI já tem um comando específico para sincronização, que é o `sync` então isso facilita muito as coisas, em geral o comando utilizado vai ser `aws s3 sync <source> <target> [--options]` e pode ser utilizado entre local x s3, s3 x local e s3 x s3.

2. No nosso caso vamos sincronizar todos os arquivos do nosso diretório que contenham a extensão .docx, então utilizaremos `aws s3 sync . s3://prcstudio3herokubucket/base`. O ponto "." é para sincronizar todos os arquivos da pasta de origem.

3. Para configurarmos a opção de deletar quando um arquivo for removido da nossa pasta local, vamos adicionar o comando `--delete`, o que consolida o comando desta forma: `aws s3 sync . to s3://prcstudio3herokubucket/base --delete`

4. Finalmente, para sincronizarmos somente as extensões desejadas vamos adicionar mais uma opção excluindo os arquivos .rb  com `--exclude "*.rb"`. 

5. Desta forma, o comando final ficou `aws s3 sync . s3://prcstudio3herokubucket/base --delete --exclude "*.rb`

6. Segue o teste criando e deletando arquivos, note que os arquivos .rb não subiram para a s3: 

[img](https://res.cloudinary.com/lztec/image/upload/v1590620687/learning-blog/2020.05.27_pi4ryr.png)

# Cron Job

1. Depois de colocar as informações necessárias do AWS SWAP em um arquivo shell script (.sh) adicionei uma rotina na tabela do cron do linux para agendar essa sincronização uma vez por dia, todo dia a 01:00. Se o computador não estiver ligado naquele horário o script executa no próximo reboot. 

2. Para acessar a crontab basta digitar na linha de comando `crontab -e` e especificar o caminho do seu script e a frequência, neste caso usei apenas a hora e o resto asterisco para mostrar que era diriamente, utilizei o crontab.guru para [ajudar](https://crontab.guru/every-day-at-1am).

# Resources 

[Amazon Commands](https://docs.aws.amazon.com/cli/latest/userguide/cli-services-s3-commands.html)