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

# Solução
Estava faltando o Absolute Path, ou seja, o arquivo não estava sendo encontrado. Diferente do projeto teste que estava rodando no ruby puro e dizia que o arquivo não tinha sido localizado, o erro no rails aparece da forma acima. Assim é preciso estudar mais sobre a manipulação de arquivos no Rails. Também considerando que este projeto será hospedado no Heroku teremos que estudar como fazer o upload destes documentos.
```
  def templater
    require "docx"
    doc = Docx::Document.open(Rails.root.join("app/controllers/base.docx").to_s)
      doc.paragraphs.each do |p|
        p.each_text_run do |tr|
          tr.substitute('_placeholder', 'teste')
        end
      end
      doc.save(Rails.root.join("app/controllers/base-edit.docx").to_s)
  end
```

# Obrigado Thanks
WaKeMaTTa - Bug Finder
Rafa Le Wagon - Bug Finder
satoryu - Gem Creator


