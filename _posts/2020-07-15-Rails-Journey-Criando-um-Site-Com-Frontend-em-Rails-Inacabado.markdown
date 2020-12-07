---
title: Rails Journey - Criando um Site com Frontend Em Rails ** Inacabado **
layout: post
tags: [linux, grep, produtividade]
---
**1**. Comecando pelo início, vou criar um projeto de Rails com database em postgres, para facilitar o deploy no Heroku. Na verdade não tem muito o que ser usado de DB, vai ser mais um site estático, de qualquer forma, melhor previnir do que remediar:

rails new vereador -d --database=postgresql

**2**. Depois vamos configurar as páginas, pensei em: home, sobre, eventos, projetos, contato

rails g controller pages home eventos projetos contato

**3**. Agora configurar o bootstrap e o Javascript, uma missão que sempre me dá dor de cabeca:

3.1. Instalar o Yarn:

curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn

3.2. Fiz uma leitura do [Assets Pipeline](https://edgeguides.rubyonrails.org/asset_pipeline.html), alguns pontos que devem ser frisados:

Antigamente os assets eram salvos em ```public```, imagens, javascripts e stylesheets. Agora o diretório correto para armazenar esses arquivos é: `app/assets`. Os arquivos serão utilizados nesta parte pelo Sprockets.

Os arquivos que ainda forem armazenados na pasta public serão considerados como arquivos estáticos. Podem ser úteis em alguns projetos. Mas lembrando sempre que o Heroku não suporta este tipo de arquivo. Para utilizar desta forma deve haver a seguinte configuraćão `config.public_file_server.enabled = true`.

Os arquivos em `app/assets` não são utilizados imediatamente como arquivos estáticos. Sempre precisarão de alguma forma de tratamento.

3.2.1 Organizacao dos Assets, confira:

```app/assets``` is for assets that are owned by the application, such as custom images, JavaScript files, or stylesheets.

```lib/assets``` is for your own libraries' code that doesn't really fit into the scope of the application or those libraries which are shared across applications.

```vendor/assets``` is for assets that are owned by outside entities, such as code for JavaScript plugins and CSS frameworks. Keep in mind that third party code with references to other files also processed by the asset Pipeline (images, stylesheets, etc.), will need to be rewritten to use helpers like asset_path.

3.2.2 Configuracão de Erro Quando não achar o Asset:

Parece ser interessante adicionar a seguinte linha no ```config/environments/development.rb``` para indicar erro na busca dos assets:

```config.assets.unknown_asset_fallback```

3.3 Arrumar o arquivo padrão da application.css para application.scss:

`app/assets/stylesheets/application.scss`

3.3.1 adicionar a seguinte linha para importar a sua scss que já estará lá na pasta conforme foi criado no rails g:

```
/* app/assets/stylesheets/application.scss */

@import "pages"; /* Will import `_pages.scss` */
```

3.3.2 Adicionar o loader no Layout padrão do Rails:

```
<%= stylesheet_link_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>
```

O turbolink é ótimo para ficar dando reload quando o arquivo for alterado.

3.3.3 Adicionar gitignore nos assets (comando do terminal):

`echo "public/assets" >> .gitignore`

3.4 Bootstrap:

No terminal digite `yarn add bootstrap`

E o popper e o jquery (dependências):

`yarn add popper.js jquery`

E importe seu bootstrap, ele vai puxar nos módulos do node:

`@import "bootstrap/scss/bootstrap";`

**Cuidado:** Retire qualquer espaco depois do ponto e vírgula.

3.5 Configure o ambiente de js em `config/webpack/environment.js` para requisitar o Wepacker:

```
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

Adicione em `app/javascript/packs/application.js`:

`import 'bootstrap';`

3.6 Se tiver algum problema com o Webpacker:

Verifique a versão do node que está instalada.

Veja a instalacão correta no Debian-Ubuntu-Mint etc [aqui](https://github.com/nodesource/distributions/blob/master/README.md)

Se estiver tudo certo, rode: `rails webpacker:install`

**4**. Arrumar as rotas:
```
Rails.application.routes.draw do
  root to: 'pages#home'
end
````

**4**. Testes:

4.1 Bootstrap:

Adicione ```<button type="button" class="btn btn-primary">Primary</button>``` em alguma das views para ver se está aparecendo no formato bootstrap.

4.2 Javascript:

