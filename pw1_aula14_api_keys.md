---
theme: default
lineNumbers: true
layout: cover
title: API Keys
author: José Roberto Bezerra
exportFilename: pw1_aula14_api_keys
colorSchema: dark
---

# {{ $slidev.configs.title }}
Programação Web 1

---

# Objetivo de Aprendizagem
- Aprofundar o conhecimento sobre APIs

---

# Agenda
- O que são API *Keys*?
- *Final Space* API
- *NASA Open* API

---
layout: section
---

# O que são API *Keys*?

---

# O que são API Keys?

- Trata-se de um **token de autenticação** usado para identificar quem está acessando umaa API
- Pode controlar:
  - Limites de uso (*rate limits*)
  - Permissões de acesso
  - Identificação de cliente

---

# Onde são usadas?

- APIs públicas ou semi-públicas
- Integrações entre sistemas
- Exemplos:
  - Google Maps API
  - OpenWeatherMap
  - Stripe, Twilio, etc.

---

# Por que usar API Keys?

- **Identificação** de quem está consumindo a API
- **Controle de acesso**
- **Limitação** de uso por cliente
- **Monitoramento e auditoria**

---

# Como gerar uma API Key?
Depende do serviço

- No painel de desenvolvedor do provedor da API
    - Exemplo: criar uma chave no site da [OpenWeatherMap](https://openweathermap.org/api)
- Mediante um cadastro
[Developer Portal Marvel](https://developer.marvel.com/signup)

---

# Exemplo prático (cliente)

```js {*}{class: '!children:text-xl'}
const axios = require('axios');

// Nunca exponha as chaves no codigo
// Utilize variaveis de ambiente (dotenv)
const API_KEY = 'sua_chave_aqui'; 

axios.get(`https://api.exemplo.com/dados?apikey=${API_KEY}`)
  .then(res => console.log(res.data))
  .catch(err => console.error(err));
```

---
layout: section
---

# *Final Space* API

---
layout: center
---

[Watch Final Space](https://finalspace.co.uk/en-US/watch/season-1/episode-1)

---
layout: quote
---

> Final Space is an American adult animated space opera comedy-drama television series created by Olan Rogers for TBS. The series involves a prisoner named Gary Goodspeed and his alien friend, Mooncake, and focuses on their intergalactic adventures as they try to solve the mystery of the titular "Final Space"

---

# Final Space API
Documentação

- Endereço base
  - [https://finalspaceapi.com/api/v0/](https://finalspaceapi.com/api/v0/)
- A API disponibiliza informações sobre os personagens
- As informações são retornadas no formato JSON
- Todas as requisições são feitas através do método GET
- Não utiliza chaves
[Documentação da API](https://finalspaceapi.com/docs/)

---

# Final Space API
*Endpoints*

- [/api/v0/character](https://finalspaceapi.com/api/v0/character)
- [/api/v0/episode](https://finalspaceapi.com/api/v0/episode)
- [/api/v0/location](https://finalspaceapi.com/api/v0/location)
- [/api/v0/quote](https://finalspaceapi.com/api/v0/quote)

---
layout: section
---

# *NASA Open* API

---

# *NASA Open* API
[Get Started](https://api.nasa.gov/)

- Demanda o uso de uma chave de API
- Para fins de teste pode utilizar `DEMO_API`
 - Limitado a 30 requisições por IP por hora
 - 50 requisições por IP por dia
- *Web Service Rate Limits*
  - 1000 requisições por hora
- Para checagem da utilização AP ver os cabeçalhos HTTP:
  - `X-RateLimit-Limit`
  - `X-RateLimit-Remaining`

---

# APOD
*Astronomy Picture of the Day*

[APOD](https://apod.nasa.gov/)

---
layout: fact
---

# Exercícios

---

# 1

Criar uma aplicação que utiliza NASA APIs APOD para buscar *links* de imagens que contenham um astro específico passado pelo usuário e que não tenha *copyright*. A aplicação deve exibir as imagens em um carrosel. **Sugestão**: Crie uma chave de API no site para melhor utilização dos recursos.

[Generate API Key](https://api.nasa.gov/#:~:text=Overview-,Generate%20API%20Key,-Authentication)

---

# 2




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
