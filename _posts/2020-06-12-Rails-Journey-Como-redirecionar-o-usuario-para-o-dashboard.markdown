---
title: Rails Journey - Como Redirecionar o Ousuário Para Seu Dashboard
layout: post
tags: [rails, dashboard, application]
---
Eu tentei várias vezes alterar o `routes` para transferir meus usuários logados para outras páginas mas isso nunca deu certo e finalmente sem querer acabei encontrando a solucao, basta criar uma funcão no application controller `app/controllers/application_controller.rb:` e adicionar o seguinte (precisa ter a Gem Devise Instalado):

```
def after_sign_in_path_for(resource)
  pages_dashboard_path
end
```
Não se esqueca de mudar o "pages_dashboard_path" para a pagina que deseja redirecionar.
