# Swagger - Open API

## DOC 

[ Documentação Swagger](https://app.swaggerhub.com/help/index)
['The OpenAPI Specification' ](https://github.com/OAI/OpenAPI-Specification/blob/master/versions/3.0.3.md)

## Requisitos

Queremos que você crie um aplicativo para ajudar pais e pacientes com distúrbios relacionados ao crescimento com base nos requisitos:

- Tela de registro da conta: Criar Conta. Uma tela que nos permite entrar, criar uma conta. Os campos devem incluir: Nome, Sobrenome, E-mail, Número de telefone, Senha, confirmar senha, Data de nascimento, Sexo e País de residência.

- Tela de Login: Faça login no aplicativo por meio das credenciais da conta de registro.

- Acompanhamento do Crescimento Infantil: Uma tela para permitir que os usuários registrem o crescimento e o progresso de uma criança com medicação. Valores como: altura, peso, perímetro cefálico, índice de massa corporal e velocidade de crescimento.

- Relatório de Crescimento Infantil: Apresentando para o usuário relatórios sobre como seu filho está progredindo. Pense nisso, os gráficos de curvas de percentual que nos permitirão monitorar seu progresso para superar possíveis problemas em seu crescimento.

## Conceitos

- **API REST**: Representational State Transfer (REST), em português Transferência Representacional de Estado, é um estilo de arquitetura de software que define um conjunto de restrições a serem usadas para a criação de web services (serviços Web). Os Web services que estão em conformidade com o estilo arquitetural REST, denominados Web services RESTful, fornecem interoperabilidade entre sistemas de computadores na Internet. Os Web services RESTful permitem que os sistemas solicitantes acessem e manipulem representações textuais de recursos da Web usando um conjunto uniforme e predefinido de operações sem estado (OBS: um protocolo sem estado (do inglês stateless) é um protocolo de comunicação que considera cada requisição como uma transação independente que não está relacionada a qualquer requisição anterior, de forma que a comunicação consista de pares de requisição e resposta independentes).

- **Swagger**: O Swagger é um framework, composto por diferentes ferramentas, que ajudam no desenvolvimento de APIs. Dentre essas ferramentas podemos destacar as de código aberto:
  - **Swagger Editor:** Um editor poderosíssimo que pode ser usado online, e que facilita (e muito) na escrita de arquivos Swagger.
  - **Swagger UI:** Uma plataforma para a geração e publicação da documentação de APIs.
  - **Swagger Codegen:** Cria SDKs para diferentes linguagens.
  - **Swagger Inspector:** Para fechar com chave de ouro. O Inspector é um serviço que testa APIs com base em um contrato Swagger.
  - **Swagger Hub**: "Empacota" isso tudo em um Software As A Service, prometendo aumentar produtividade e colaboração entre times no que tange desenvolvimento de APIs.

* **Open API**: É como ficou renomeado o Swagger Specification em 2016, tornando-a assim em uma especificação "vendor-neutral" (A neutralidade do fornecedor é uma abordagem de negócios e design que visa garantir ampla compatibilidade e intercambiabilidade de produtos e tecnologias. O modelo abrange padronização, princípios de design não proprietários e práticas comerciais imparciais. ). O Swagger (framework) "gira em torno" do OpenAPI (antigo Swagger Specification), provendo ferramentas para a modelagem e documentação. É sem dúvida uma combinação espetacular, e não a toa é a mais famosa e eficiente no momento.

# Especificação

## Especificação Autenticação de usuário

- **Qual é o path?**<br />
  /login POST
- **Quais são os parâmetros do request?**<br />

- **Qual é o formato da resposta?**<br />
  JSON
- **Qual é o formato do request?**<br />
  JSON
- **Qual é o request body (corpo da requisição)?**<br />
  email e password
- **Qual é o response body (corpo da resposta)?**<br />
  token, id, email, firstName e lastName
- **Qual é o status da resposta para operação de sucesso?**<br />
  200 - ok
- **Qual é a resposta para operação de erro no request?**<br />
  400 - Dados request enviados incorretos
- **Quais são as respostas para operações de erro de regra de negógio?**<br />
  401 - Password incorreto<br />
  404 - Usuário não encontrado<br />
- **Qual é a resposta para operação de erro no servidor?**<br />
  500 - Erro no servidor

## Especificação para criação da conta de usuário

- **Qual é o path?** <br />
  /accounts GET<br />
  /accounts POST<br />
  /accounts/{id} GET<br />
  /accounts/{id} PUT<br />
  /accounts/{id} DELETE<br />

- **Quais são os parâmetros do request?**<br />
  token JWT HEADER<br />
  {id} account PATH, quando necessário
- **Qual é o formato da resposta?**<br />
  JSON
- **Qual é o formato do request?**<br />
  JSON
- **Qual é o request body (corpo da requisição)?**<br />
  id, firstName, lastName, email, phoneNumber. password, dateBirth e gender
- **Qual é o response body (corpo da resposta)?**<br />
  id, firstName, lastName, email, phoneNumber, dateBirth e gender
- **Qual é o status da resposta para operação de sucesso?**<br />
  200 - OK GET<br />
  201 - Criado POST<br />
  202 - Aceito<br />
  204 - Sem conteúdo<br />
- **Qual é a resposta para operação de erro no request?**<br />
  400 - Dados request enviados incorretos<br />
- **Quais são as respostas para operações de erro de regra de negógio?**<br />
  401 - Token invalido, inexistente ou expirado<br />
  404 - Recurso {id} não encontrado
- **Qual é a resposta para operação de erro no servidor?**<br />
  500 - Erro no servidor

## Especificação para inclusão dos dados de crescimento da criança

- **Qual é o path?** <br />
  /progress GET<br />
  /progress POST<br />
  /progress/{id} GET<br />
  /progress/{id} PUT<br />
  /progress/{id} DELETE<br />
- **Quais são os parâmetros do request?**<br />
  token JWT HEADER<br />
  {id} progress PATH, quando necessário
- **Qual é o formato da resposta?**<br />
  JSON
- **Qual é o formato do request?**<br />
  JSON
- **Qual é o request body (corpo da requisição)?**<br />
  id, height, weight, headCircumference, dateProgress e account(id, email, firstName,dateBirth, gender e lastName)
- **Qual é o response body (corpo da resposta)?**<br />
  id, height, weight, headCircumference, dateProgress e account(id, email, firstName,dateBirth, gender e lastName)
- **Qual é o status da resposta para operação de sucesso?**<br />
  200 - ok GET<br />
  201 - Criado POST<br />
  202 - Aceito PUT<br />
  204 - Sem conteúdo DELETE<br />
- **Qual é a resposta para operação de erro no request?**<br />
  400 - Dados request enviados incorretos
- **Quais são as respostas para operações de erro de regra de negógio?**<br />
  401 - Token invalido, inexistente ou expirado<br />
  404 - Recurso {id} não encontrado
- **Qual é a resposta para operação de erro no servidor?**<br />
  500 - Erro no servidor

## Especificação relatório de desempenho de crescimento da criança

- **Qual é o path?** <br />
  /accounts/{email}/progress GET
- **Quais são os parâmetros do request?**<br />
  token JWT HEADER<br />
  {email} accounts PATH
- **Qual é o formato da resposta?**<br />
  JSON
- **Qual é o formato do request?**<br />
  JSON
- **Qual é o request body (corpo da requisição)?**<br />

- **Qual é o response body (corpo da resposta)?**<br />
  height, weight, headCircumference, dateProgress
- **Qual é o status da resposta para operação de sucesso?**<br />
  200 - ok
- **Qual é a resposta para operação de erro no request?**<br />
  400 - Dados request enviados incorretos
- **Quais são as respostas para operações de erro de regra de negógio?**<br />
  401 - Token invalido, inexistente ou expirado<br />
  404 - Recurso {email} não encontrado<br />
- **Qual é a resposta para operação de erro no servidor?**<br />
  500 - Erro no servidor
