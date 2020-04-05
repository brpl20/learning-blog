---
title: \[Rails Journey] Dia 3 - Novos Objetivos e Ideias
layout: post
tags: [rails, objetivos, ideias, organizacao]
---
# Objetivo 2
* Criar um Docx; :metal:
* arrumar problema entre gem _estadocivil_ x _estado_

Estava pensando que eu tinha um [problema](https://github.com/ruby-docx/docx/issues/79#issuecomment-608707167), com a gem, mas acabou sendo que o problema era só a forma que eu estava criando os campos. Vou mudar a forma de cria-los direto no .docx para não gerar mais confusão. Os campos do db vou acabar deixando igual.

Acabei aprendendo como alterar uma gem e testa-la localmente, basta clonar a gem localmente e alterar a origem da gem também para o local:

`# Local Gem Tests Branches Etc gem 'docx', :path => '/home/brpl19/code/pellibr/docx'`

# Objetivos Alterados
Conforme eu fui desenvolvendo e pensando no projeto, achei melhor mudar algumas coisas. O objetivo inicial era fazer o javasccript e também melhorar um pouco o frontend, fazendo um pouco de tudo.

Mas eu encontrei algumas dificuldades em desenvolver a ideia do workflow do aplicativo. Até poderia usar o Figma ou algum sistema parecido de wireframe para configurar tudo antecipadamente, mas como não sei exatamente como o sistema vai se desenrolar, decidi por focar 100% no backend e depois ir para o frontend com mais embasamento e ideia mais certa do como o projeto vai se desenvolver.

Essa abordagem também é útil porque será mais fácil se eu precisar terceirizar o front end. A meta é que o site seja 100% funcional com um trabalho HTML puro, sem Js de frontend (apenas as lógicas dos formulários) e sem CSS. Assim dá pra delinear de modo mais fácil o trabalho necessário de front.

# Objetivo 4
* ver bug do formulário no simpleforms radio buttons
* criar models e controllers para criar um novo:
  * advogado
  * escritório de advocacia
  * advogado parceiro
  * estagiário
  * trabalho
* criar updates e destroy
* injetar dados básicos pré definidos
  * Exemplo: Gênero :masculino :feminino uma vez que esses dados vão ser fixos, não há necessidade de alteração

# To Do
* rails generate controller pages contact about


#Objetivos FrontEnd
* Esconder e criar condicionais de formulário no JavaScript/CSS;
* Melhorar formatação e organização do Formulário : Criar tabelas do bootstrap para sites responsivos;
* Implementar Select2;

#Objetivo 5
* bug db :estadocivil :point_right: esqueci da informação no strong params, :see_no_evil:
