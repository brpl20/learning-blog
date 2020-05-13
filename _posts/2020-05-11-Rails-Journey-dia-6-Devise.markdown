---
title: Rails Journey Dia 6 - Instalando e Configurando o Devise
layout: post
tags: [rails, devise]
---
Finalmente vou instalar o [devise](https://github.com/heartcombo/devise), que basicamente é uma biblioteca de autenticação, vou buscar customizar esta ferramenta bem como customizar sua aparência, verificar emails com js e enviar emails para os novos usuários.

# Primeiro Passo: Instalação Inicial 
gemfile -> `gem 'devise'`

rode no terminal do seu projeto -> `bundle install`

em seguida instale com -> `rails g devise:install`

adicione em -> `config/environments/development.rb` 
-> `config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }`

crie um arquivo com esse caminho e nome -> `app/views/layots/_alerts.html.erb`
adicione -> 

```
<p class="notice"><%= notice %></p>
<p class="alert"><%= alert %></p>
```

Para ficar ainda melhor mude os alertas com as condicionais adequadas para dar a resposta correta ao usuário de acordo com o que for chamado pelo devise, inclusive com o bootstrap: 
```
<% if notice %>
  <p class="alert alert-success"><%= notice %></p>
<% end %>
<% if alert %>
  <p class="alert alert-danger"><%= alert %></p>
<% end %>
```

invoque no seu layout principal -> `app/views/layots/application.html.erb` com a linha -> `<%= render 'layouts/alerts' %>`

Remova todas as linhas eventuais dos seus view no `show.html.erb` que contenham o notice -> `<p id="notice"><%= notice %></p>`


Isso deixa seu código mais bonito e profisisonal. Até aqui apenas instalamos o devise, que criou alguns arquivos de configuração e inicializaçãomo como o config/initializers/devise.rb e config/locales/devise.en.yml e as instruções que seguimos foram do próprio devise quando se adiciona o comando de instalação inicial. 


## Criando as Routes - BUG “No route matches [GET] ”/users/sign_out"?: 

Me deparei com este bug e demorei um pouco para resolver, mas ainda acredito que a solução não é boa pois altera a metodologia de funcionamento do devise e não descobri exatamente o que causou este erro. 

Teoricamente basta constar a `devise_for users` no seu `routes.rb` para que o devise crie todas as rotas para deletar, criar, autenticar sessões e destruir sessões dos usuários, conforme consta na [documentação](https://www.rubydoc.info/github/heartcombo/devise/master/ActionDispatch/Routing/Mapper%3Adevise_for) entretanto, não consegui fazer funcionar de jeito nenhum, alterando várias vezes as rotas. 

Só achei a solução no StackOverFlow alterando a forma de postar no link, alterando de Delete para Get, conforme consta [aqui](https://stackoverflow.com/questions/28555793/why-the-error-no-route-matches-get-users-sign-out).



## Resources: 
[rails girls](https://guides.railsgirls.com/devise)

