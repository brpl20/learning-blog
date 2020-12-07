---
title: Como converter todos arquivos da pasta com FFMPEG
layout: post
tags: [aprendizados, ffmpeg, linux]
---
# Como converter todos arquivos da pasta com FFMPEG

```
for i in *.MP4; do name=`echo "$i" | cut -d'.' -f1`
  echo "$name"
  ffmpeg -i "$i" -c:v mpeg2video -q:v 5 -c:a mp2 -f vob "${name}.mpg"
done
```

* Primeira Linha: para cada arquivo .MP4 (cuidado com o _case sensitive_) faça uma variável com o nome do arquivo. Depois de declarar essas variáveis ele concatena mais um comando com o pipe "&#124;|" recortando a extensão do arquivo com o comando cut.
* Segunda Linha: Apenas para printar a variável.
* Terceira Linha: Comando do `ffmpeg` contendo como arquivo de origem o "i" que foi puxado com o looping da primeira linha, depois os demais comandos do ffmpeg e finalmente o mesmo nome declarado na variável + a extensão desejada.
