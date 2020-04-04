# Swagger - Open API

[ Documentação Swagger](https://app.swaggerhub.com/help/index)

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


