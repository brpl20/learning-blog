---
title: Rails - Criando um Helper
layout: post
tags: [rails, ruby, helper]
---
Hoje como eu estava trabalhando no frontend resolvi criar um helper para me ajudar a trabalhar com arquivos .svg, uma vez que o Rails ainda não oferece esse helper especifico depois de ler um post no [SOF](https://stackoverflow.com/questions/36986925/how-do-i-display-svg-image-in-rails). 

Basicamente é só criar um módulo dentro de um arquivo na pasta _app/helpers_ e chamar quando necessário: `<%= show_svg('undraw_fill_forms_yltj.svg') %>`.
{% highlight ruby %}
  def show_svg(path)
    if path.include? 'svg'
      File.open("app/assets/images/#{path}", "rb") { |file| raw file.read }
    else
      File.open("app/assets/images/#{path}.svg", "rb") { |file| raw file.read } 
      end
  end
end
{% endhighlight %}

> Só deixei a lógica da extensão para aceitar com e sem extensão. Só vai dar problema se constar svg no meio do arquivo, mas também não é algo muito comum. Depois tenho que mudar o helper para que ele busque na AWS. 

Só depois de fazer o helper eu descobri que tem um pronto e muito melhor em uma gem chamada [inline_svg](https://github.com/jamesmartin/inline_svg) :rage:. Mas o que importa é o aprendizado.