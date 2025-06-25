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

- Um **token de autenticação** usado para identificar quem está acessando uma API
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
- **Limitação de uso por cliente**
- **Monitoramento e auditoria**

---

# Como gerar uma API Key?

Depende do serviço. Exemplos:

- No painel de desenvolvedor do provedor da API
    - Exemplo: criar uma chave no site da [OpenWeatherMap](https://openweathermap.org/api)
- Mediante um cadastro

---

# Exemplo prático (cliente)

```js {*}{class: '!children:text-xl'}
const axios = require('axios');

// Nunca exponha as chaves no codigo
// Utilize variaveis de ambiente
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

---



---
layout: section
---

# *NASA Open* API

---

---


---
layout: fact
---

# Exercícios

---

# 1


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
