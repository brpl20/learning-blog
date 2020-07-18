---
title: Rails e Jekyll - Criando um Rake File Para UPdate no Github
layout: post
tags: [Rails, Jakyll, Github, Automação]
---
Já falei aqui como criar alguns arquivos de shell para automatizar o update no github e outras funções.

Descobri que também é possível fazer isso através do Rakefile, basta criar uma (sem extensão alguma, apenas `Rakefile`) e adicionar ao repositório central do seu projeto, neste caso de Jekyll, com as seguintes informações:

```
desc "Publish to yout blog"
task :publish do
  system "git add ."
  message = "Site updated at #{Time.now.utc}"
  system "git commit -m #{message.inspect}"
  system "git push origin master"
end
```

Depois basta digitar no diretório do seu projeto `rake publish`.
