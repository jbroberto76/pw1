---
theme: olive_JRB
size: 16:9
math: katex
paginate: true
title: Aula 4 - Bootstrap - PW1
description: Aula 4 - Bootstrap - PW1
author: José Roberto Bezerra
url: https://ifce.edu.br/fortaleza
image: https://marp.app/og-image.jpg

---
<!-- _class: lead _paginate: false -->
# Programação Web 1
## **Bootstrap**

---
<!-- class: invert -->
# Objetivo de Aprendizagem
- Trilhar os primeiros passos para utilização do *Framework* CSS Bootstrap

---
# Agenda
- *Quickstart*
- Primeiro *Laytout*
- Componentes
- Repositório de exemplos

---
<!-- _class: lead _paginate: false -->
# **Quickstart**

---
# **HTML Base**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Basic HTML File</title>
</head>
<body>
    <h1>Hello, world!</h1>
</body>
</html>
```

[Bootstrap Tutorial](https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-get-started.php)

---
# Primeiro passo

Adicionar *viewport* (Cabeçalho)
- ```<meta name="viewport" content="width=device-width, initial-scale=1">```

Adicionar os arquivos necessários pelo Bootstrap
```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
```

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
```

---
# **HTML Base v2**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Basic Bootstrap Template</title>
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" 
    rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" 
    crossorigin="anonymous">
</head>
<body>
    <h1>Hello, world!</h1>
    <!-- Bootstrap JS Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
</body>
</html>
```

---
<!-- _class: lead _paginate: false -->
# **Elementos de Layout**

---
# Container
- Elemento de design fundamental
- Uso obrigatório quando um grid é utilizado (quase sempre)
- *Containers* são usadas para:
    - envelopar ou envolver um determinado conteúdo
    - alinhar conteúdo na página

---
# Tipos de *Container*
- ```.container```
- ```.container-fluid```
- ```.container-{breakpoint}```

---
# ```.container```
## Cria um container de tamanho fixo em diferentes **breakpoints**
```html
<div class="container">
    <h1>This is a heading</h1>
    <p>This is a paragraph of text.</p>
</div>
```

[Boostrap Tutorial](https://www.tutorialrepublic.com/codelab.php?topic=bootstrap&file=responsive-fixed-width-container)

---
# ```.container-fluid```
## Cria um container de 100% da largura da tela, sempre

```html
<div class="container">
    <h1>This is a heading</h1>
    <p>This is a paragraph of text.</p>
</div>
```
[Bootstrap Tutorial](https://www.tutorialrepublic.com/codelab.php?topic=bootstrap&file=fluid-container)

---
# ```.container-{breakpoint}```
## Container que ocupa 100% da largura de tela em pontos de quebra (*breakpoints*)
```html
<div class="container-sm">100% wide until screen size less than 576px</div>
<div class="container-md">100% wide until screen size less than 768px</div>
<div class="container-lg">100% wide until screen size less than 992px</div>
<div class="container-xl">100% wide until screen size less than 1200px</div>
```

[Bootstrap Tutorial](https://www.tutorialrepublic.com/codelab.php?topic=bootstrap&file=specify-responsive-breakpoints-for-containers)

---
# Adicionando Bordas e Fundos
```html
<!-- Container with dark background and white text color -->
<div class="container bg-dark text-white">
    <h1>This is a heading</h1>
    <p>This is a paragraph of text.</p>
</div>
<!-- Container with light background -->
<div class="container bg-light">
    <h1>This is a heading</h1>
    <p>This is a paragraph of text.</p>
</div>
<!-- Container with border -->
<div class="container border">
    <h1>This is a heading</h1>
    <p>This is a paragraph of text.</p>
</div>
```

---
# Grid System
- Facilita a criação de *layouts* responsivos de qualquer formato e tamanho
- Utiliza **12** colunas
- Tamanhos
    - X-Small, xs (<576px)
    - Small, sm (>=576px)
    - Medium, md (>=768px)
    - Large, lg (>=992px)
    - X-Large, xl (>=1200px)
    - XX-Large, xxl (>=1400px)

---
# Criando um layout de Duas Colunas
```html
<div class="container">
    <!--Row with two equal columns-->
    <div class="row">
        <div class="col-md-6">Column left</div>
        <div class="col-md-6">Column right</div>
    </div>
</div>
```

[Bootstrap Tutorial](https://www.tutorialrepublic.com/codelab.php?topic=bootstrap&file=two-column-grid-layouts-for-tablets-and-desktops)

---
# Layout de Duas Colunas iguais
```html
<div class="container">
    <!--Row with two equal columns-->
    <div class="row">
        <div class="col">Column one</div>
        <div class="col">Column two</div>
    </div>
</div>
```

---
# Outros Layouts
- [Multicolunas](https://www.tutorialrepublic.com/lib/images/grid-system-illustration.jpg)
- [Aninhados](https://www.tutorialrepublic.com/codelab.php?topic=bootstrap&file=nested-columns)
- [Colunas de tamanho automático](https://www.tutorialrepublic.com/codelab.php?topic=bootstrap&file=size-columns-based-on-the-width-of-their-content)

---
# Exemplo Layout Fixo

[Exemplo 1](https://www.tutorialrepublic.com/codelab.php?topic=bootstrap&file=fixed-layout)

---
# Exemplo Layout Fluído

[Exemplo 2](https://www.tutorialrepublic.com/codelab.php?topic=bootstrap&file=fluid-layout)

---
# Exemplo Layout Responsivo
[Exemplo 3](https://www.tutorialrepublic.com/codelab.php?topic=bootstrap&file=responsive-layout)

---
<!-- _class: lead _paginate: false -->
# **Outros Elementos de Layout**

---
# Tipografia
- Cabeçalhos (```<h1>``` a ```<h6>```)
- Parágrafos (```<p>```)
- Citações (```<blockquote>```)

[Exemplos](https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-typography.php)

---
# Botões
![](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-buttons.png)

```html
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-info">Info</button>    
<button type="button" class="btn btn-dark">Dark</button>
<button type="button" class="btn btn-light">Light</button>
<button type="button" class="btn btn-link">Link</button>
```

---
# Botões

[Exemplos de botões](https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-buttons.php)

---
# Cards

![](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-card.png)

---
# Cards
![](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-card-with-header-and-footer.png)

---
# Cards

![height:400px](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-card-with-multiple-content-types.png)

[Exemplos de Card](https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-cards.php)

---
# Navbar
![](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-static-navbar.png)

![](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-navbar-with-logo.png)

![](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-navbar-color-schemes.png)

---
# Navbar

[Exemplos de Navbar](https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-navbar.php)

---
# Tabelas

![](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-simple-table.png)

![](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-table-with-accented-rows.png)

---
# Tabelas
[Exemplos de Tabela](https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-tables.php)

---
# Formulários

![](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-disabled-forms.png)

[Exemplos de Forms](https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-forms.php)

---
# Outras fontes de consulta
- [Tutorial Bootstrap 5.3](https://getbootstrap.com/docs/5.3/getting-started/introduction/)
- [Repositório de Temas](https://startbootstrap.com/)
- [Tutorial W3Schools](https://www.w3schools.com/bootstrap5/)

---
<!-- _class: lead _paginate: false -->
# **Exercícios**

---
# Exercício 1

Utilizando o Bootstrap, criar layouts similares a atividade proposta na aula anterior (Atividade Layouts). Adicione conteúdo de preenchimento.

---
# Exercício 2

Escolha um tema de sua preferência para criar um site. Utilize o Bootstrap para criar toda a parte visual. Escolha um dos layouts criados na aula anterior e adicione os seguintes elementos:
- Navbar (com nomes de seções reais)
- Cards 
- Tabelas
- Formulários
- Texto

Crie um projeto do *GitHub* e poste na Atividade Bootstrap.

**Sugestão**: utilize o tema a ser adotado para o trabalho final da disciplina PW1.

---
# Referências
- https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/