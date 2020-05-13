---
title: Rails Journey Dia 5 - Frontend - Bootstrap e JS
layout: post
tags: [rails, frontend, css]
---
Iniciei hoje o trabalho com frontend, a ideia era deixar para depois que eu estivesse com o back todo configura, porém isso não se mostrou muito viável em razão de ser importante ter uma noção de como o usuário irá interagir com o aplicativo, construindo a ideia aos poucos junto com o backend.

Hoje fiquei mais na parte de configurações de HTML, CSS e SCSS, iniciando os aplicativos e configurações iniciais, que são um pouco chatas na primeira "pegada". 

1. Instalar o Yarn: 
```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn
```

2. Scss Partials
A maior diferença agora é para criar os SCSS partials, iniciando com _ . Por exemplo \_home.scss que pode ser importado no arquivo através do @. 
```
@import "home";
```

3. Não esqueça de criar o arquivo `application.scss` na `app/assets/stylesheets/` para substituir o css original. 

4. Os Scss já estão sendo carregados no layout
```
<%= stylesheet_link_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>
```

5. Adicione o bootstrap com yarn 
`yarn add bootstrap`

6. Adicione uma linha no import do application.scss 
`@import "bootstrap/scss/bootstrap";`

7. Adicione responsividade ao bootstrap conforme os navegadores 
```
<!-- Bootstrap Response -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
```

8. Confira se a gem _webpacker_ está no seu gemfile. Se não estiver adicione. Também confira se esta linha está no seu layout da application (app/views/layouts/application.html.erb):
```
<%= javascript_pack_tag 'application', 'data-turbolinks-track': 'reload', defer: true %>
```

9. Adicione o popper.js e o jquery: 
```
yarn add popper.js jquery
```

10. As vezes preciso instalar o babel também com o comando `babel-cli` *não* use somente `babel` senão vai pegar uma versão antiga. 

11. Configure o environment do webpack:
```
// config/webpack/environment.js
const { environment } = require('@rails/webpacker')

// Bootstrap 4 has a dependency over jQuery & Popper.js:
const webpack = require('webpack')
environment.plugins.prepend('Provide',
  new webpack.ProvidePlugin({
    $: 'jquery',
    jQuery: 'jquery',
    Popper: ['popper.js', 'default']
  })
)

module.exports = environment
```

12. Finalmente, adicione uma linha no : `app/javascript/packs/application.js` --- Note que este arquivo será diferente se tiver ocorrido tudo certo do que o arquivo original que tinha várias linhas e barras //=. 
```
import 'bootstrap';
 ```

## Thanks: 
A maior parte deste material foi feito com base no bootcamp da [Le Wagon](https://www.lewagon.com/)

## Resources: 
Hoje utilizei os seguintes recursos: 

[Undraw: ilustrações variadas em SVG](https://undraw.co)

[CSS Tricks - Using SVG](https://css-tricks.com/using-svg/)

Google Fonts

Bootstrap
