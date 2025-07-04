---
theme: default
lineNumbers: true
layout: cover
title: API + CRUD
author: José Roberto Bezerra
exportFilename: pw1_aula15_api_crud
colorSchema: dark
---

# {{ $slidev.configs.title }}
Programação Web 1

---

# Objetivo de Aprendizagem
- Construir uma API com acesso a bancos de dados

---

# Agenda
- CRUD
- CRUD + REST

---
layout: section
---

# CRUD

---
layout: quote
---

> *Create, Read, Update* e *Delete* são as quatro funções elementares que modelos de bancos de dados deve implementar. Paradigma popular no desenvolvimento de *software*, especialmente na *web*.

[What is CRUD?](https://www.codecademy.com/article/what-is-crud-explained)

---

# REST API

```mermaid
architecture-beta
    group api

    service db(database)[Database] in api
    service server(server)[Web Server] in api
    service cloud(cloud) in api

    service WebApp(logos:aws)
    db:L -- R:server
```

---

# REST API

```plantuml
@startuml Serverless API
' from https://github.com/awslabs/aws-icons-for-plantuml/blob/main/examples/Serverless%20API.puml

!define AWSPuml https://raw.githubusercontent.com/awslabs/aws-icons-for-plantuml/v18.0/dist
!include AWSPuml/AWSCommon.puml
!include AWSPuml/AWSExperimental.puml
!include AWSPuml/ApplicationIntegration/APIGateway.puml
!include AWSPuml/Compute/Lambda.puml
!include AWSPuml/Database/DynamoDB.puml
!include AWSPuml/General/Client.puml
!include AWSPuml/Groups/AWSCloud.puml
!include AWSPuml/Storage/SimpleStorageService.puml

' Groups are rectangles with a custom style using stereotype - need to hide
hide stereotype
skinparam linetype ortho
skinparam rectangle {
    BorderColor transparent
}

rectangle "$ClientIMG()\nClient" as client
AWSCloudGroup(cloud){
  rectangle "$APIGatewayIMG()\nAmazon API\nGateway" as api
  rectangle "$LambdaIMG()\nAWS Lambda\n" as lambda
  rectangle "$DynamoDBIMG()\nAmazon DynamoDB\n" as dynamodb
  rectangle "$SimpleStorageServiceIMG()\nAmazon S3" as s3
  rectangle "$LambdaIMG()\nAWS Lambda" as trigger

  client -right-> api: <$Callout_1>\n
  api -right-> lambda: <$Callout_2>\n
  lambda -right-> dynamodb: <$Callout_3>\n
  api -[hidden]down-> s3
  client -right-> s3: <$Callout_4>
  s3 -right-> trigger: <$Callout_5>\n
  trigger -[hidden]up-> lambda
  trigger -u-> dynamodb: <$Callout_6>\n
}
@enduml
```

---
layout: fact
---

# Exercícios

---

# 1

Criar uma aplicação que utiliza NASA APIs APOD para buscar *links* de imagens que contenham um astro específico passado pelo usuário e que não tenha *copyright*. A aplicação deve exibir as imagens em um carrosel. **Sugestão**: Crie uma chave de API no site para melhor utilização dos recursos.

[Generate API Key](https://api.nasa.gov/#:~:text=Overview-,Generate%20API%20Key,-Authentication)

---

# Referências
- [Final Space API](https://finalspaceapi.com/)
- [NASA Open API](https://api.nasa.gov/)

---
layout: end
---

# Prof. {{ $slidev.configs.author }}
jbroberto@ifce.edu.br
<br><br>
<PoweredBySlidev />