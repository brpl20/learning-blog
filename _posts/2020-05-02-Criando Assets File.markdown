---
title: Criando um assets file
layout: post
tags: [rails, ruby, helper, assets, frontend]
---
Novamente mais uma dica aprendida na Le Wagon. 

As vezes estamos navegando nos projetos e temos sempre alguns arquivos de css ou js repitidos (ou de qualquer coisa), como por exemplo _navbar, header, footer, buttons, colors, form_. Ou mesmo arquivos de sistema como configurações por exemplo. 

Para facilitar este trabalho é interessante criar um arquivo .zip e upar ele para o github ou deixar em alguma pasta na sua nuvem ou backup, depois basta fazer um 

{% highlight shell %}
	rm -rf app/assets/stylesheets # remove os arquivos do stylesheets
	curl -L ttps://github.com/github/rails-stylesheets/archive/master.zip > stylesheets.zip # busca os arquivos no seu repositório
	unzip stylesheets.zip -d app/assets && rm -f stylesheets.zip && rm -f app/assets/rails-stylesheets-master/README.md #remove os arquivos e limpa os desnecessários como o README.md
	mv app/assets/rails-stylesheets-master app/assets/stylesheets # move para a pasta desejada
{% endhighlight %}
