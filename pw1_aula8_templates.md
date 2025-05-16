---
theme: default
lineNumbers: true
layout: cover
title: Templates
author: José Roberto Bezerra
exportFilename: pw1_aula8_templates
colorSchema: dark
---

# Programação Web 1
*Templates*

---

# Objetivos de Aprendizagem
- O que são *Template Engines*?
- Instalar o *Template Engine* EJS
- Utilizar funções básicas de *templates* em geral

---

# Agenda

- *Template engines*
- Instalação
- Exemplo de aplicação com EJS

---
layout: section
---

# *Template Engines*

---
layout: quote
---

# O que são *Template Engines*?

> *Template engines* são especialmente úteis em projetos que requerem a geração de HTML dinamicamente. Permitem que os desenvolvedores insiram dados em *templates* (modelos) pré-definidos, resultando em páginas web personalizadas e desenvolvidas rapidamente.

---

# Exemplos
Com Express podem ser utilizados diversos TE.

- [Pug](https://pugjs.org/api/getting-started.html)
- [Handlebars](https://handlebarsjs.com/)
- [EJS](https://ejs.co/)

---

# EJS

> EJS is a simple templating language that lets you generate HTML markup with plain JavaScript.

---
layout: section
---

# Instalação

---

# Como usar o EJS?

- Para aplicar o *template engine* EJS há dois caminhos
    1. Com Express Generator
    2. Sem o Express Generator

---

# Instalação
EJS com Express Generator

- `npm install express express-generator --view=ejs` (Rever Aula 7)
- Para utilizar o EJS com Express, bastam duas linhas de configuração no `app.js`:

```js {*}{class: '!children:text-lg'}
// define o caminho a partir de /views
// válido apenas com o Express Generator
app.set('views', path.join(__dirname, 'views'));
// define o EJS como template engine
app.set('view engine', 'ejs');
```

- Observe que a linha 3 apenas é necessária caso o Express Generator seja utilizado

---

# Instalação
Sem Express Generator

- Os *templates* devem estar em `/views`
- Note que nas linhas 8 e 12 os caminhos são especificados a partir de `/views`

```js {5,9}{class: '!children:text-lg'}
app.set('view engine', 'ejs');
// res.render carrega o template ejs especificado
// o uso da extensão é opcional
app.get('/', function(req, res) {
    res.render('pages/index');
});
// about
app.get('/about', function(req, res) {
    res.render('pages/about');
});
app.listen(8080);
console.log('8080 is the magic port');
``` 

---
layout: two-cols-header
---

# Organização dos arquivos

::left::

- Todos os *templates* devem estar organizados em `/views`
- É interessante organizar em subdiretórios para melhor organização. Por exemplo:

::right::

```plantuml
@startwbs
*_ <&folder> ""myapp""
**_ ""package.json""
**_ ""app.js""
**_ ""routes""
**_ ""views""
***_ <&folder> ""partials""
****_ ""<&file>header.ejs""
****_ ""<&file>footer.ejs""
****_ ""<&file>sidebar.ejs""
****_ ""<&file>adds.ejs""
***_ ""<&file>index.ejs""
***_ ""<&file>layout.ejs""
***_ ""<&file>error.ejs""
@endwbs
```

---

# `/partials`

- A palavra chave quando se usa *templates* é **REUTILIZAÇÃO**
- O diretório `/partials` (sugestão de nome) deve conter tudo aquilo que for reutilizável:
    - Cabeçalhos
    - Rodapés
    - Barras de menu
    - *Sidebars*
    - Anúncios

---
layout: section
---

# Exemplo de aplicação com EJS

---

# Exemplo de aplicação

1. Crie uma aplicação com Express Generator ou crie uma aplicação com a estrutura de arquivos e diretórios abaixo.
    1. `npm init -y`
    2. `npm install express express-generator`
    3. `npx express-generator --view=ejs`

```plantuml
@startwbs
*_ <&folder> ""myapp""
**_ ""package.json""
**_ ""app.js""
**_ ""routes""
**_ ""views""
***_ <&folder> ""partials""
@endwbs
```

---

# Exemplo de aplicação

2. Caso opte pelo EG toda a estrutura já será criada.
3. Em `/partials` crie os arquivos `footer.ejs` e `header.ejs`
4. Em `/views` crie o arquivo `magic.ejs`

---

# `header.ejs`

```html {*}{class: '!children:text-lg'}
<!DOCTYPE html>
<html lang="en">
<head>
   <meta charset="UTF-8">
   <title>Random Title</title>
   <!-- CSS link (loading Semantic UI from a CDN) -->
   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css" />
   <style>     body { padding:50px; }   </style>
</head>
<body class="container">
<header>
   <div class="ui inverted menu">
       <a class="item" href="/">Home</a>
       <a class="item" href="/magic">Magic</a>
   </div>
</header>
```


---

# `footer.ejs`

```html {*}{class: '!children:text-lg'}
<div class="ui inverted footer">
   <div class="ui container">
     Topcoder 2021. All Rights Reserved
   </div>
</div>
```


---

# Exemplo de aplicação
Como usar as partials?

5. Para inserir o `header.ejs` na *view* (Linha 1) em `index.ejs` 
6. Para inserir o `footer.ejs` na *view* (Linha 10)

```js {*}{class: '!children:text-lg'}
<%- include('./partials/header') %>
  <main>
    <div class="ui segment">
      <h1>Index Route</h1>
      <p>This is the INDEX route</p>
    </div>
  </main>

  <footer>
    <%- include('./partials/footer') %>
  </footer>

  </body>
</html>
```

---

# `magic.ejs` 

```js {*}{class: '!children:text-lg'}
<%- include('./partials/header') %>
  <main>
    <div class="ui segment">
      <h1>Magic Route</h1>
      <p>This is a magic route</p>
    </div>
  </main>

  <footer>
    <%- include('./partials/footer') %>
  </footer>

  </body>
</html>
```

---

# Exemplo de aplicação

7. Em `/routes` criar o arquivo `magic.js`

```js {*}{class: '!children:text-lg'}
var express = require('express')
var router = express.Router()

router.get('/', function(req, res, next) {
  res.render('magic')
})

module.exports = router;
```

---

# Exemplo de aplicação

8. Incluir a rota `/magic` em `app.js`

```js {*}{class: '!children:text-lg', startLine: 9}
var magicRouter = require('./routes/magic')
```

```js {*}{class: '!children:text-lg', startLine: 25}
app.use('/magic', magicRouter)
```

9. Teste todas as rotas

---

# Exemplo de aplicação
Estrutura final

```plantuml
@startwbs
*_ <&folder> ""myapp""
**_ ""package.json""
**_ ""app.js""
**_ ""routes""
***_ "" index.js""
***_ "" magic.js""
***_ "" users.js""
**_ ""views""
***_ <&folder> ""partials""
****_ ""<&file>header.ejs""
****_ ""<&file>footer.ejs""
***_ ""<&file>index.ejs""
***_ ""<&file>magic.ejs""
***_ ""<&file>users.ejs""
***_ ""<&file>error.ejs""
@endwbs
```

---
layout: fact
---

# Perguntas

---
layout: fact
---

# Exercício

---

# 1
Refazer o exercício #3 da Aula 7 (Atividade Router) adicionando um *template* para cada uma das rotas. Utilize um cabeçalho e um rodapé compartilhado em um diretório `/partials`

---

# Referências
- [Embedded JavaScript templating](https://ejs.co/)
- [Using EJS Template Engine With Express.js](https://www.topcoder.com/thrive/articles/using-ejs-template-engine-with-express-js)

---
layout: end
---

# Prof. José Roberto Bezerra
jbroberto@ifce.edu.br