---
title: Como usar REGEX (Expressões Regulares) para evitar codificação no Sublime Text (e outros editores)
layout: post
tags: [Sublime Text, REGEX]
---
# Como usar REGEX (Expressões Regulares) para evitar codificação no sublimetext (e outros editores)

Abaixo podemos ver um exemplo de codificação repetitiva, precisamos adicionar o ", label" em todas as linhas, como fazer isso de forma simples e rápida?

Imagem...

Talvez alguma forma de selecionar apenas o fim da palavra? Seria muito bom, mas eu ainda não sei essa função no SublimeText, apenas selecionar com o CTRL + MOUSE, o que também não é muito viável...

Assim, vou usar a busca do REGEX

Depois de alguma pesquisa chego a conclusão que o melhor o operador do REGEX é:
https://stackoverflow.com/questions/1751301/regex-match-entire-words-only

{% highlight regex %}
  \:(\w+)
  #\: para puxar apenas o :
  #\w+ para separar apenas palavras inteiras
{% endhighlight %}

# Resultado no Sublime:
**Antes:**


![screenshot_antes](https://res.cloudinary.com/lztec/image/upload/v1586463469/regex2_toyugj.png)


**Seleção Realizada:**
![screnshot_seleção](https://res.cloudinary.com/lztec/image/upload/v1586463469/regex_fwq6zh.png)


**Depois:**

![screenshot_depois](https://res.cloudinary.com/lztec/image/upload/v1586463469/regex1_eje7gj.png)


_Obrigado pela hospedagem [Cloudinary](https://cloudinary.com/)_

# Conclusão
Demorei bem mais tempo pesquisando e criando este post do que simplesmente fazendo manual, mas o que importa é o aprendizado, espero utilizar esta técnica muitas vezes e conseguir economizar tempo. Provavelmente existe uma forma mais fácil de fazer isso, quando eu escobrir eu vou adicionar aqui.

# Resources:
[regexr](https://regexr.com/)
[rubular](https://rubular.com/)
[mozilla rgx](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide/Regular_Expressions)
[regex101](https://regex101.com/)
[regex quickstart](https://www.rexegg.com/regex-quickstart.html)
[regex for noobs](https://www.janmeppe.com/blog/regex-for-noobs/)
