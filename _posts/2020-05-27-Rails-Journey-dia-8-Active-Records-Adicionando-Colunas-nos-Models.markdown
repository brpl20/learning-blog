---
title: Rails Journey Dia 8 - Adicionando colunas novas nos models
layout: post
tags: [rails, devise]
---

Trabalhar com banco de dados sempre é complicado, especialmente com o projeto em andamento. Mas é uma realidade que não pode ser evitada e com o Rails, essa missão é muito mais simples do que parece. 

Para adicionar novos campos basta criar um gerador de coluna para o seu model, no nosso exemplo tempo o model: **Client** e queremos criar uma informação nova, neste caso uma lista de documentos, que será no formato de JSON e se chamará **documents**.

Basta executar: 

```
rails g migration add_documents_to_clients documents:json
rails db:migrate
```

Esse é um campo interno, ou seja, não vai constar nos formulários, apenas para listar os documentos e metadatas para acessa-los posteriormente, neste caso toda informação será criada internamente pelo código Ruby do Controller, não se esqueça de salvar, como no exemplo abaixo.

```
client.documents = {client.id, user.id, proc.docx}
client.save
```