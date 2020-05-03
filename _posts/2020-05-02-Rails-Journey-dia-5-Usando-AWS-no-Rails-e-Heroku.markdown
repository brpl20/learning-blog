---
title: Rails Journey Dia 5 - Usando AWS no Rails e Heroku
layout: post
tags: [rails, heroku, active storage, aws]
---
A config da aws levou um pouco mais de trabalho do que eu pensava, segue um manual super simplificado. Este post assume que já existe uma conta Heroku e na AWS (Amazon Web Services), bem como a configuração do S3 Bucket da AWS na região parecida com a do Heroku que está rodando seu aplicativo. 

# Crie suas credenciais na amazon. 
```
conta > Minhas Credenciais de Segurança > Chaves de Acesso > Criar Novas Chaves de Acesso
```
Após a criação é criado a chave de acesso (KEY) e a chave secreta (SECRET), nada mais que um monte de número e letras. 

**ATENÇÃO!!!** 

> Nunca, jamais compartilhe esta senha com ninguém. Pode gerar danos catastróficos a sua conta na AWS e muito menos ESQUEÇA no código fonte do seu projeto e encaminhe para o GitHub. Há hackers que ficam monitorando isso o tempo todo em busca de novas brechas. Inclusive o próprio Github e a amazon monitram isso, inclusive irão te ligar para que exclua a chave e você crie novas metodologias de segurança nos seu app. Ou seja, mesmo se ninguém pegar sua chave, vai dar uma baita dor de cabeça. 

# Adicione a Gem da AWS no seu projeto e rode o _bundle_
Não adicione simplesmente a aws-sdk senão o sistema irá puxar várias gemas inúteis ao seu projeto.
`gem "aws-sdk-s3", require: false `

# Configure seu arquivo de storage -- _storage.yml_
Há duas formas de cofigurar, usando o .env e usando o rails credentials. Eu tentei as duas formas e preferi o _credentials_:

```
amazon:
  service: S3
  access_key_id: <%= Rails.application.credentials.dig(:aws, :access_key_id) %>
  secret_access_key: <%= Rails.application.credentials.dig(:aws, :secret_access_key) %>
  region: '' # esse campo pode ser em texto mesmo
  bucket: '' # esse campo também pode ser somente em texto 
```

# Configure o credentials do Rails 
`$ EDITOR=vim rails credentials:edit`

Adicione suas credenciais no local indicado, tire os comentários, arrume a identação para não ter problema (2 espaços).

> Não esqueça de apertar `i` para entrar no insert mode e depois `Ctrl+V` para colar, e finalmente `:w` para salvar (write) e `:q` para sair (ainda sei muito pouco de VIM).

# Arrume o Storage padrão do rails, mudando de local para o AWS em _/config/environments/development.rb_:
```
config.active_storage.service = :amazon
```

# Criando um código para baixar e trabalhar com arquivos 
Para trabalhar com os arquivos da amazon, criei esse código, criei uma config e depois um cliente novo, provavelmente exista um método melhor, uma vez que esse está um pouco lento. Todo ele é para fazer uma sessão no aws3 e buscar um arquivo no bucket. O método `body` é para trabalhar abrir o arquivo da forma adequada e trabalhar com ele:
```
require 'aws-sdk-s3'
require 'docx'

aws_config = Aws.config.update({
	region: 'us-west-2', 
	credentials: Aws::Credentials.new(
    Rails.application.credentials.dig(:aws, :access_key_id),
    Rails.application.credentials.dig(:aws, :secret_access_key)
    )})

aws_client = Aws::S3::Client.new

aws_doc = aws_client.get_object(bucket:'bucketname', key:'docx.docx')
aws_body = aws_doc.body

```

## Resources: 
[heroku info s3](https://devcenter.heroku.com/articles/s3)

[heroku info active storage](https://devcenter.heroku.com/articles/active-storage-on-heroku)

[aws ruby sdk](https://docs.aws.amazon.com/sdk-for-ruby/v3/developer-guide/s3-example-create-buckets.html)

[rails active storage](https://guides.rubyonrails.org/active_storage_overview.html#amazon-s3-service)

[sof question](https://stackoverflow.com/questions/41118606/missing-region-use-region-option-or-export-region-name-to-envaws-region)

[aws sdk ruby gem](https://github.com/aws/aws-sdk-ruby)

[editando crednetials no rails](https://medium.com/cedarcode/rails-5-2-credentials-9b3324851336)