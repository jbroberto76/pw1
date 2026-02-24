---
theme: default
transition: fade
colorSchema: dark
lineNumbers: true
layout: image
image: /cover.svg
description: Programação Web 1
author: José Roberto Bezerra
title: Aula Zero
exportFilename: pw1_aula0
---

# {{ $slidev.configs.title }}
{{ $slidev.configs.description }}

---

# Objetivos de Aprendizagem

- Definir os conceitos gerais de PW
- Conhecer a metodologia da disciplina

---

# Agenda

- O que é Programação Web?
- Conceitos e Tecnologias
- Metodologia

---
layout: section
---

# Conceitos de PW

---
layout: quote
---

> **Desenvolvimento Web** (Programação Web) é o processo de construir aplicações (*sites*) utilizando tecnologias implantadas em servidores remotos acessíveis através da Internet.

---
layout: image
backgroundSize: contain
image: https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Extensions/Server-side/First_steps/Client-Server_overview/basic_static_app_server.png
---

# *Sites* Estáticos

---
layout: image
backgroundSize: contain
image: https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Extensions/Server-side/First_steps/Client-Server_overview/web_application_with_html_and_steps.png
---

# *Sites* Dinâmicos

---

# Desenvolvimento *Web*

- Frontend
- Backend
- Fullstack

---
layout: quote
---

# Desenvolvimento *Frontend*

> O **Frontend** é responsável pela interface do usuário e pela experiência de interação com o sistema. É o que o usuário vê e interage diretamente no navegador.

---

# Desenvolvimento *Frontend*
Principais responsabilidades

- *Design* da interface gráfica (UI)
- Experiência do usuário (UX)
- **Responsividade** e acessibilidade
- Interações dinâmicas (ex.: cliques, animações)

---

# Desenvolvimento *Frontend*
Tecnologias Típicas

- HTML5: Estrutura o conteúdo web <logos-html5 />
- CSS3: Estiliza e organiza o layout <logos-css3 />
- JavaScript: Adiciona interatividade <logos-javascript />
- *Frameworks*: React, Angular, Vue.js <logos-react /> <logos-angular-icon /> <logos-vue />

---

# Desenvolvimento *Frontend*
Atividades Típicas

- Criação de botões, menus, formulários
- Garantir que o site funcione bem em dispositivos móveis e de mesa
- Implementar animações e transições
- Visual adequado para aplicação (Cores, fontes, *layout*, etc)

---
layout: quote
---

# Desenvolvimento *Backend*

> O **Backend** envolve a lógica na retaguarda da aplicação, priorizando a interação com bancos de dados, autenticação e outras funcionalidades essenciais que acontecem no servidor e são transparentes ao usuário.

---

# Desenvolvimento *Backend*
Principais responsabilidades

- Processamento de dados e lógica de negócios
- Gerenciamento de banco de dados
- Autenticação e autorização de usuários
- Integração com APIs e serviços externos

---

# Desenvolvimento *Backend*
Tecnologias Típicas

- Linguagens de programação: Python, Java, Ruby, PHP, Node.js
	- <logos-python /> <logos-java /> <logos-ruby /> <logos-php /> <logos-nodejs />
- Bancos de dados: MySQL, PostgreSQL, MongoDB
	- <logos-mysql /> <logos-postgresql /> <logos-mongodb-icon />
- APIs: RESTful, GraphQL
- Servidores: Apache, Nginx

---

# Desenvolvimento *Backend*
Atividades típicas

- Armazenamento e recuperação de dados de um banco de dados
- Autenticação de usuários
- Criação de APIs para comunicação com o *frontend*

---
layout: quote
---

# Desenvolvimento *Fullstack*

> Aplicado por alguns desenvolvedores que reúnem as habilidades tanto de FE quanto de BE.

---

# Desenvolvimento *Fullstack*
Principais responsabilidades

- Combinar habilidades de *frontend* e *backend*
- Entender todo o ciclo de desenvolvimento de uma aplicação
- Integrar APIs, banco de dados e lógica de interface

---

# Desenvolvimento *Fullstack*
Tecnologias Típicas

- Linguagens e *frameworks* *Fullstack*: Node.js, Ruby on Rails, Django
	- <logos-nodejs /> <logos-ruby /> <logos-django-icon />
- Conhecimento de tecnologias de *frontend* e *backend*
- Ferramentas DevOps: Docker, Kubernetes, CI/CD <logos-docker-icon /> <logos-kubernetes /> 

---

# Desenvolvimento *Fullstack*
Exemplos de atividades

- Desenvolver uma aplicação completa, desde a interface até a lógica no servidor.
- Implementar segurança na autenticação e autorização.
- Integração de banco de dados com a interface do usuário.

---

| Característica               | Frontend                          | Backend                          | Fullstack                        |
|------------------------------|-----------------------------------|----------------------------------|----------------------------------|
| **Objetivo**            | Interface e interação do usuário  | Lógica de negócios  | Ambos, frontend e backend        |
| **Tecnologias**    | HTML, CSS, JavaScript, Frameworks | Linguagens de servidor, bancos   | Combinação de frontend e backend |
| **Atividades**    | Design responsivo, UX, UI         | Criação de APIs, autenticação    | Desenvolvimento completo         |
| **Responsabilidade**          | Estética e usabilidade            | Funcionalidade e desempenho      | Equilíbrio entre usabilidade e funcionalidade |
| **Desafios**           | Acessibilidade, compatibilidade   | Escalabilidade, segurança        | Manter o equilíbrio entre os dois lados |

---
layout: section
---

# Que caminho seguir?

---
layout: center
---

> *Frontend*: Se você é criativo, gosta de *design* e da interação com o usuário.

> *Backend*: Se você prefere lidar com lógica, servidores e a manipulação de dados.

> *Fullstack*: Se você quer ter uma visão global do desenvolvimento e gosta de trabalhar com todos os aspectos de uma aplicação.

---

# Tecnologias e Ferramentas
PW1

- HTML5 <logos-html5 />
- CSS3 <logos-css3 />
- Node.js (Express) <logos-nodejs />
- APIs REST
- Postman <logos-postman />
- MongoDB <logos-mongodb-icon />
- Git <logos-git-icon />
- Visual Studio Code <logos-visual-studio-code /> (ou IDE de preferência) 

---
layout: fact
---

# Por que?

---
layout: quote
---

# *Stack Overflow* <logos-stackoverflow />
2025 *Developer Survey*

> This annual Developer Survey provides a crucial snapshot into the needs of the global developer community, focusing on the tools and technologies they use or want to learn more about.

---

# *Programming, scripting, and markup languages* 
- [*Most popular technologies*](https://survey.stackoverflow.co/2025/technology#1-programming-scripting-and-markup-languages)
- [*Admired and Desired*](https://survey.stackoverflow.co/2025/technology#2-programming-scripting-and-markup-languages)

---

# *Databases*
- [*Most popular technologies*](https://survey.stackoverflow.co/2025/technology#1-databases)
- [*Admired and Desired*](https://survey.stackoverflow.co/2024/technology#2-databases)

---

# *Web frameworks*
- [*Most popular technologies*](https://survey.stackoverflow.co/2025/technology#1-web-frameworks-and-technologies)
- [*Admired and Desired*](https://survey.stackoverflow.co/2025/technology#2-web-frameworks-and-technologies)

---

# *Integrated development environment*
- [*Most popular technologies*](https://survey.stackoverflow.co/2025/technology#1-dev-id-es)
- [*Admired and Desired*](https://survey.stackoverflow.co/2025/technology#1-dev-id-es)

---
layout: fact
---

# PW1 2026.1

---

# Metodologia
PW1 2026.1

* A cada aula
	- Abordagem de um conceito específico
	- Demonstrações de código exemplificando o conceito
	- Até 50 minutos de exposição
	- Atividades didáticas
* Atividades avaliativas em algumas aulas (N1)

---

# Metodologia
PW1 2026.1

* Trabalho final (N2) 
	- Individual
	- Tema livre
	- Criação de aplicação com funcionalidades, interação com usuário e uso de bancos de dados

---
layout: fact
---

# Perguntas

---

# Referências
- [*Web development*](https://developer.mozilla.org/en-US/docs/Learn)
- [Arquitetura Cliente/Servidor](https://developer.mozilla.org/pt-BR/docs/Learn/Server-side/First_steps/Client-Server_overview)
- [Stack Overflow 2025 Survey](https://survey.stackoverflow.co/2025/)

---
src: /snippets/end.md
---