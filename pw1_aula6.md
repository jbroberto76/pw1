---
theme: neversink
layout: cover
color: navy
colorSchema: navy
exportFilename: pw1_aula6
---

# Express
*Minimalist Web Framework*

---
layout: side-title
color: navy
align: lm-lm
---

:: title ::
# Objetivo de Aprendizagem
:: content ::
- Conhecer os conceitos fundamentais do *framework* Express

---
layout: top-title
color: navy
---

:: title ::
# Agenda
:: content ::
- Funcionamento básico
- *Middlewares*
- Rotas

---
layout: top-title-two-cols
color: navy
---

:: title ::
# Funcionamento Básico
:: left ::
- No arquivo ```app.js``` mostrado
    1. Importação do Express
    2. Instanciação do objeto ```app```
    3. Inicia um servidor na porta 3000 para atender requisições GET
    4. Exibe uma mensagem no console
:: right ::
```js
const express = require('express');
conts app = express();
const PORT = 3000;

app.get('/', (req, res) => {
    res.send('Hello, world!')
});
```

---
layout: top-title-two-cols
color: navy
---

:: title ::
# Tratamento de Requisição
:: left ::
- ```req``` requisições recebidas pelo servidor vindas do cliente
- ```res``` respostas enviadas pelo servidor para o cliente
:: right ::
```js
app.get('/', (req, res) => {
    res.send('Hello, world!')
});
```

---
layout: quote
color: navy
---

> Routing refers to determining how an application responds to a client request to a particular endpoint,
which is a URI (or path) and a specific HTTP request method (GET, POST, and so on).

[Roteamento Básico](https://expressjs.com/en/starter/basic-routing.html)



---
layout: top-title
color: navy
---

:: title ::
# Referências
:: content ::
- [Express](https://expressjs.com/)
- [Nodemon]()
- [PM2](https://pm2.io/)
- [Express](https://expressjs.com/)