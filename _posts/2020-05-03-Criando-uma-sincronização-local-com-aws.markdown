---
title: Criando uma sincronização local script, cron e aws 
layout: post
tags: [aws, linux]
---
Nest post irei criar uma sincronização entre minha pasta local de trabalho com arquivos determinados para a pasta da amazon aws. Estou assumindo a criação na conta da Aws, bem como seu bucket específico.

# Primeiro Passo: Aws Credentials

Antes de rodar os comandos ou rodando eles você irá esbarrar em uma mensagem de erro pedindo as credenciais, rode o `aws configure` e insira seu key e chave secreta. [Mais aqui.](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html) 

# Segundo passo: Comandos Aws 

Instale o [aws sdk](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2-linux.html#cliv2-linux-install), basicamente é um comando para acessar a máquina da sdk, com praticamente tudo que você faria no seu linux local, como por exemplo `aws s3 ls` para ver a lista de arquivos ou buckets. `cp` para copiar. `rm` para remover. `mv` para mover. `mb` de "make bucket" para criar um bucket.  

# Terceiro passo: Sync 

Depois busque a pasta local que você deseja, como por exemplo `~/aws_sync` e simplesmente rode o comando: 

`aws s3 sync ~/aws_sync . s3://bucket`

Ou simplesmente `aws s3 sync . s3://bucket` se você já estiver na pasta desejada, ele vai assumir o próprio local para sincronização. O '.' pega todos os arquivos do diretório. É possível selecionar, excluir e fazer uma série de filtros nesta sincronização. 

Essa sincronização que eu criei é apenas de ida, ou seja, só vai enviar os arquivos para a S3, não vou utilizar os arquivos que estão na bucket. Deixo eles somente no modo de leitura e crio outros arquivos na s3 se precisar edita-los.

# Quarto Passo: Criar um script 

Já tenho um post sobre scripts, confira [aqui](https://pellibr.github.io/learning-blog/2020/03/20/configurando-um-shell-script-para-atualizar-o-git-no-jekyll.html). 

Neste caso vou criar um para fazer o upload, ainda não sei se as credenciais ficam armazenadas definitivamente na máquina, mas veremos. **Cuidado:** ainda tenho que testar este script no caso de deletar arquivos, conflitos etc. 

{% highlight shell %}
  aws s3 sync ~/aws_sync . s3://bucket
{% endhighlight %}


# Quinto Passo: Criar um cron job
Pendente

## Resources: 
[aws client commands](https://docs.aws.amazon.com/cli/latest/userguide/cli-services-s3-commands.html)

[aws s3 reference](https://docs.aws.amazon.com/cli/latest/reference/s3/)

[agendador de tarefas cron](https://www.youtube.com/watch?v=cL1v4CL0b6A&t=619s)
