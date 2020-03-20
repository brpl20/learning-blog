---
title: BUG You have already activated i18n Jekyll
layout: post
tags: [jekyll, bugs]
---
##Para arrumar o bug ou similares:##

check_for_activated_spec!': You have already activated i18n 1.8.2, but your Gemfile requires i18n 0.9.5. Prepending `bundle exec` to your command may solve this. (Gem::LoadError)

##Faça o seguinte:##

É um bug de conflito de versões do i18n que é uma gem de internacionalização, ocorre quando há um conflito de versões, geralmente pela instalação das gems do Rails e especialmente depois que a configuração do blog é alterada para o GitHub.

1. Para corrigir basta criar um arquivo de configuração local (config.dev.yml) com as configurações originais do Jekyill, ou só removendo os dados do GitHub e a pasta base dos posts.

2. Rodar o Jekyll com o seguinte comando, assim ele não irá conflitar com as configurações online do seu Jekyll:{% highlight bash %}bundler exec jekyll serve --config config.dev.yml{% endhighlight %}

3. O ideal é criar um arquivo .sh (Shell Script) com esta configuração para evitar retrabalhos.

###Resources:###
[:
-------------
[superuser][superuser]
[superuser]: https://superuser.com/questions/1483914/jekyll-serve-error-after-updating-ruby-bundler-and-jekyll]
Resources
