---
title: Rails Journey - Dia 4 - Trabalhando com Models 
layout: post
tags: [rails, models, migrations]
---
**Cuidar com os novos fields do DB:** Quando você adicionar novos fields no seu projeto rails, novas tabelas e relações entre as tabelas, sempre tome cuidado com os campos requeridos nas entradas de banco de dados anteriores, é preciso criar uma condicional permitindo que a view possa ignorar esses campos (abaixo) ou é preciso tratar registros da sua db antes de finalizar a atualização. Também é preciso lembrar dos `params` no controller. 

```
   	<p> <% if article.category_id.nil? %>
   	<p style="color:red;">	<%= "Sem Categoria Definida" %> </p>
   		<% else %>
   	<p>	<%= link_to "#{article.category.name}", root_path(:category => "#{article.category.name}"), :method => :post %> </p>
   		<% end %> 
```

**Conferir se funciona no Rails C antes:** Outra boa prática para testar os relacionamentos e novas tableas é fazer alguns testes no console `rails c` e verificar a integridade das informações e a forma de chama-los.