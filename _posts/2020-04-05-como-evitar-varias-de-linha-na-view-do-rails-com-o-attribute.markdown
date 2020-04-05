---
title: como evitar varias de linha na view do rails com o attribute
layout: post
tags: [rails, views]
---

Geralmente vamos ter algo assim na view, organizando as informações conforme a nossa necessidade

```
<h2> <%= @client[:nome] %> </h2>
<h2> <%= @client[:sobrenome] %> </h2>
<p> <%= @client[:id] %> </p>
```

Msa podemos utilizar um looping com `for attributes`, fica mais ou menos assim:

```
<% for attribute in @user.attributes.keys %>
  <p><%= attribute.humanize %> <%= @user.attributes[attribute].to_s %></p>
<% end %>
```

## Referências

[Confira aqui outras formas de organizar melhors os atributos](https://stackoverflow.com/questions/1031175/rails-easy-way-to-display-all-fields-in-view)
