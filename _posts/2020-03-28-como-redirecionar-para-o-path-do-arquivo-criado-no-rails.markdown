---
title: como redirecionar para o path do arquivo criado no rails
layout: post
tags: [rails, file]
---
Depois de criar um arquivo (como no post anterior) por exemplo .Docx ou .PDF. Você pode redirecionar o user direto para a pasta de download. Neste caso usamos a pasta `/public/` para colocar os arquivos. Acredito que exista algo melhor, colocando em um db separado por exemplo com [Cloudinary](https://cloudinary.com/), mas vai ficar para uma implementação futura:

```
  def create
    @client = Client.new(client_params)
    if @client.save
      templater
      redirect_to '/files/base-edit.docx'
      # Antes estava voltando ao client Path
      # Mas não é possível deixar dois redirects
      # redirect_to clients_path
    else
      render :new
    end
  end
```
