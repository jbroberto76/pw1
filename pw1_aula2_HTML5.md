---
theme: default
lineNumbers: true
layout: image-right
transition: fade
image: /jose-campos-zRkBOOpKRhs-unsplash.jpg
title: HTML5
author: José Roberto Bezerra
description: Programação Web 1
exportFilename: pw1_aula2_HTML5
colorSchema: dark
---

# {{ $slidev.configs.title }}
{{ $slidev.configs.description }}

---

# Objetivos de aprendizagem
- Revisar os conceitos fundamentais do HTML
- Conhecer as principais novidades do HTML5

---

# Agenda
- Componentes de um site
- Medição de desempenho
- HTML5

---
layout: section
---

# Componentes de um site

---

![](/jens_kitchen.png)

---

# Componentes

- Página principal (HTML)
- Estilo (CSS)
- Informação visual (*Design*)
- Comportamento

---

# `index.html`
```html
<!DOCTYPE html>
<html>
    <head>
        <title>Jen's Kitchen</title>
        <link rel="stylesheet" href="kitchen.css" type="text/css" >
    </head>
<body>
    <h1><img src="foods.gif" alt="food
    illustration"> Jen&rsquo;s Kitchen</h1>
    <p>If you love to read about <strong>cooking and eating</strong>, would like to find 
    out about of some of the best restaurants in the world, or just want a few choice 
    recipes to add to your collection, <em>this is the site for you!</em></p>
    <p><img src="spoon.gif" alt="spoon illustration"> Your pal, Jen at Jen's Kitchen</p>
    <hr>
    <p><small>Copyright 2011, Jennifer Robbins</small></p>
</body>
</html>
```

---

# `kitchen.css`

```css
body { 
    font: normal 1em Verdana;
    margin: 1em 10%;
    }
h1 { 
    font: italic 3em Georgia;
    color: rgb(23, 109, 109);
    margin: 1em 0 1em;
    }
img { 
    margin: 0 20px 0 0; 
    }
h1 img { 
    margin-bottom: -20px; 
    }
small {
     color: #666666; 
     }
```

---
image: /jens_kitchen2.png
layout: image
backgroundSize: contain
---

---

# Informação visual

- Atenção do usuário
- Apelo visual
- PNG, JPEG, SVG

---
image: /myfirst_SVG.png
layout: image-right
backgroundSize: contain
---

# SVG

```html
<html>
    <body>
        <h1>My first SVG</h1>
        <svg width="100" height="100" xmlns="http://www.w3.org/2000/svg">
            <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow">
        </svg>
    </body>
</html>
```

---

# *Scalable Vector Graphics*
- Gráficos vetoriais para web
- Podem ser animados
- É uma recomendação do W3C
- Integra-se a outros padrões: CSS, JavaScript, etc

---

# Comportamento
- Dinamismo
- Ações personalisadas
- Comportamento segundo condições
- JS, PHP, Python, Ruby, C#, etc

---
layout: section
---

# Medição de Desempenho

---

# Princípios
- Limitar o tamanho dos arquivos
- Reduzir a quantidade de requisições

---

# Ações Práticas
- Otimizar o tamanho das imagens sem comprometer a qualidade
- Minimizar o tamanho de arquivos HTML e CSS (remover espaços em branco e quebras de linha)
- Manter o mínimo necessário de JS
- Usar apenas o necessário em termos de imagens, scripts ou bibliotecas JS
- Reduzir a quantidade de requisições
- HTTP/2

---

# Como Medir o Desempenho?

- *Google Chrome* <logos-chrome />
    - View > Developer > Developer Tools
    - Clique em Network
    - Carregue uma página web
- *Firefox* <logos-firefox />
    - Ferramentas > Ferramentas do Navegador > Ferramentas de Desenv Web
    - Clicar em Rede
    - Recarregar a página

---

# Como Medir o Desempenho?
- *Edge* <logos-microsoft-edge />
    - CTRL + SHIFT + I

---
layout: section
---

# HTML5 <logos-html-5 />

---

# DOCTYPE
- Declaração inicial de todos os documentos HTML5
- `<!DOCTYPE html>`
- Validação HTML5
    - Processo de checagem do código segundo as especificações do W3C
- Validadores HTML5
    - [https://validator.w3.org/](https://validator.w3.org/)
    - [https://html5.validator.nu/](https://html5.validator.nu/)

---
layout: two-cols-header
---

# HTML mínimo

::left::

- *Document Type Declaration*
- `<html>` é dividido em `<head>` e `<body>`
- `<head>` contém informações sobre o documento
- `<body>` contém tudo que deve ser visível, renderizado

::right::
```html{all|1-2,10|3-6|7-9}{class:'!children:text-xl'}
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset='utf-8'>
        <title>Title here</title>
    </head>
    <body>
        Page content goes here
    </body>
</html> 
```

---

# Tag `<p>`
- Elemento mais simples
- Pode conter texto e imagens
- Não pode conter cabeçalhos e listas
- Fechamento opcional no HTML5, obrigatório no XHTML

---

# Cabeçalhos
- *Headings*
- Facilita a busca por informações no documento
- Mais destaque `<h1>`
- Menos destaque `<h6>`

---

# Listas
- Ordenadas `<ol>`
- Não ordenadas `<ul>`

---

# Listas Ordenadas
```html{*}{class:'!children:text-xl'}
<ol start="4">
<li>item</li>
<li>new item</li>
</ol>
```
<ol start="4">
<li>item</li>
<li>new item</li>
</ol>

---

# Listas Não Ordenadas
```html{*}{class:'!children:text-xl'}
<ul>
    <li>item</li>
    <li>new item</li>
</ul>
```

<ul>
    <li>item</li>
    <li>new item</li>
</ul>

--- 

# Tabelas
- Exibição de dados tabulares
- Organização do documento
- [HTML table basics](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Tables/Basics)

---

# Imagens
- [Imagens no HTML](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML)
- `<img src="dinossauro.jpg" />`
- `<img src="img/dinossauro.jpg" />`
- `<img src="https://www.example.com/images/dinosaur.jpg" />`

---

# Organizando o Conteúdo
- HTML5 oferece novas maneiras de organizar e **identificar** o
conteúdo dos documentos além do elemento `<div>`
- Documentos longos são organizados em capítulos ou seções, etc
- HTML5 oferece elementos alternativos
    - `section`, `article`, `aside` e `nav`
- Elementos úteis em conjunto com CSS

---

# Tags `<article>` e `<section>`
```html
<article>
    <h1>Get to Know Helvetica</h1>
    <section>
        <h2>History of Helvetica</h2>
        <p></p>
    </section>
    <section>
        <h2>History of Helvetica</h2>
        <p></p>
    </section>
</article>
```

---

# Tag `<aside>` (Sidebar)
- Identifica conteúdo complementar
```html
<aside>
<h2>Web Font Resources</h2>
    <ul>
        <li>Typekit</li>
        <li>Google Fonts</li>
    </ul>
</aside>
```

---

# Tag `<nav>`
- Identifica elementos de navegação
- Muito utilizado em dispositivos de leitura
```html
<nav>
    <ul>
        <li>Serif</li>
        <li>Sans-serif</li>
        <li>Script</li>
    </ul>
</nav>
```

---

# Tags `<header>` e `<footer>`

- Não possuem nenhuma função visual
- São utilizados em conjunto com folhas de estilo para identificação e *formatação* de forma precisa

---

# Exemplo de `<span>`

```html{*}{class:'!children:text-xl'}
// O elemento <span> está sendo usado para colorir uma parte do texto
<p>Eu tenho olhos <span style="color:blue">azuis</span>.</p>
```

---

# Exemplo de `<div>`

```html{*}{class:'!children:text-xl'}
// Todos os elementos dentro da <div> recebem o estilo
<div style="color:red">
    <h1>Red</h1>
    <p>Em todas as tags</p>
</div>
```

---
layout: quote
---

> Os elementos `<div>` e `<span>` são complementados por atributos `id` e `class`

---

# Atributo `id`

> Especifica uma identificação **única** em um elemento HTML. Por exemplo, `<div id=button_send>`.

---

# Atributo `class`

> Especifica uma classe para um elemento HTML. Por exemplo, `<div id=button_menu>`.

---

# Exemplo

```html{*}{class:'!children:text-xl'}
<button id="botao_adicionar" class="botao_cardapio">Adicionar</button>
<button id="botao_filtro" class="botao_cardapio">Filtrar</button>
```

---
layout: fact
---

# Perguntas

---
layout: fact
---

# Exercícios

---

# 1
Usando as ferramentas de medição de desempenho mostradas, carregue uma página com grande quantidade de elementos. Por exemplo, site de notícias, Youtube e similares.
- Quanto tempo levou para carregar a página?
- Quais os elementos que levaram mais tempo para carregar?
- Em quanto tempo a página foi carregada?
- Recarregue a página e observe quanto tempo leva o carregamento. Levou menos tempo?

---

# 2
Use um dos validadores HTML5 para validar o site [https://www.monographcomms.ca/](https://www.monographcomms.ca/). Baixe o código fonte da página (Clique com botão direito em qualquer ponto da página e em seguida *View Page Source*). Faça alterações no código fonte da página para reduzir eventuais erros, avisos e informações tornando o arquivo compatível com HTML5. Faça *prints* do relatório do validador antes e depois das alterações. Poste os relatório na atividade Validação HTML5 no Google Classroom.

(Atividade Validação HTML5)

---
layout: fact
---

# Perguntas

---

# Referências
- [HTML Tutorial W3 Schools](https://www.w3schools.com/html/)
- [Tutotial HTML MDN](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [Tutorial SVG](https://www.w3schools.com/graphics/svg_intro.asp)
- [W3C](https://www.w3.org/)

---
src: /snippets/end.md
---