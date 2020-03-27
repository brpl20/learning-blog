---
title: \[Rails Journey] Primeiros Passos
layout: post
tags: [rails, LOG]
---
Enfim estou criando meu primeiro webapp em Rails. É uma ferramenta para auxíliar minha rotina no escritório, automatizando o processo de geração de documentos.

Algo que tenho aprendido é conquistar pequenos objetivos, um cada vez, enfrentando também, um bug de cada vez, vamos começar.

## Objetivo 1
  * Criar um rails `rails new prc` :thumbsup:
  * Enviar para o git :thumbsup:
  * Criar a DB Simples :thumbsup:
  * Criar um cliente (Client.new) com simpleform :thumbsup:
  * Criar uma home (sem design) com o botão para criar o cliente novo :thumbsup:
  * Criar um Simple Form (sem design) para Criação e uma View dos Clientes

## LOG:
```
  rails g model Client genero:boolean nome sobrenome nacionalidade estadocivil capacidade profissao empresa_atual nascimento:date nome_mae nb rg cpf email endereco cidade estado dados_bancarios cep telefone notas

  rails db:create db:migrate

  rails generate controller clients

  rails g controller pages home

  rails s ... (webpacker e simpleform messages)

  rails webpacker:install

  rails g simpleform:install

  rails s



```

## Erros e Bugs
* Erro na configuração do model colocando incorretamente o attr_acessor, estava dando conflito.
* Erro no strong params (próximo post)

## Próximo Objetivo
* Melhorar formatação e organização do Formulário
* Esconder campos do formulário
* Criar condicionais de Formulário no JavaScript/CSS

## Estudos Necessários
* Melhorar bootstrap : Parte Flex e mudanças com o Simple Form
* Simple Form

## Aprendizados
* Manter um LOG de ações como este (pode ajudar no futuro)
* Manter um controle de coisas a serem feitas
* Criar um arquivo mind
* Ter paciência, resolver um problema por vez
* Pesquisar e aprender sozinho, mas não ter vergonha de pedir ajuda quando está travado

## Referências
[jlongster](https://jlongster.com/How-I-Became-Better-Programmer)
1. Find people who inspire you, but don't idolize them.
2. Don't devalue your work.
1. Don't feel pressured to work all the time.
1. Ignore fluff.
> Here's a question I like to ask: do you spend most of your time making your code look "nice"? If so, I recommend not focusing on it so much. Your code is going to change a lot over time anyway. It's better to focus hard on the core problems you're trying to solve and think hard about your layers of abstractions. After you've nailed all of that you can spend a little time polishing your code. (This also applies to the DRY principle. Don't worry about it so much. Feel free to duplicate.)
5. Dig into past research.
> If you're excited about an idea, it's super tempting to sit down an immediately get going. But you shouldn't do that until you've done some cursory research about how people have solved it before. Spending a few days researching the topic always completely changes how I am going to solve it.
6. Outras: *Learn C, Write a Compiler, Learn Macros, SICP, Understand Continuations, New language*






