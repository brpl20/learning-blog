---
title: Ruby Gem Bug
layout: post
tags: [ruby, gems, rails]
---
O objetivo do projeto é criar um sistema que o usuário crie documentos novos com base em templates, para isso estamos usando a gema 'Docx'. Entretanto no momento de criar o código temos um problema de Classe.

[Repository](https://github.com/pellibr/prc3)

[Ruby Gem - Docx](https://github.com/ruby-docx/docx)

*Bug*
O bug acontece na criação do usuário, quando vamos usar a função templater (abaixo) que requer a gema expecífica para gerar o documento:
```
NoMethodError in ClientsController#create
`undefined method `close' for nil:NilClass`
```
[Image](https://imgur.com/a/j6kopyE)

*Controller*
```
  def templater
    require "docx"
    doc = Docx::Document.open("base.docx")
      doc.paragraphs.each do |p|
        p.each_text_run do |tr|
          tr.substitute('_placeholder', 'teste')
        end
      end
      doc.save('base-edit.docx')
  end
```

*Gemfile*
`gem 'docx', :require => ["docx"]`

_Já tentei outras formas também, sem o require por exemplo, mas o erro continua._
