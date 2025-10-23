# Node.js & SQLite: Desenvolvimento Ágil e Eficiente

## 🎯 Objetivos da Apresentação
- Entender a combinação Node.js + SQLite
- Conhecer casos de uso ideais
- Aprender implementação prática
- Explorar vantagens e limitações

---

## 1. 📚 Introdução

### O que é SQLite?
- **Banco de dados embutido**
- **Zero configuração** - não requer servidor
- **Arquivo único** - todo o banco em um arquivo `.sqlite` ou `.db`
- **Auto-contido** - não depende de processos externos

### Por que Node.js + SQLite?
```javascript
// Simplicidade de integração
const sqlite3 = require('sqlite3').verbose();
const db = new sqlite3.Database('./app.db');
```

---

## 2. 🚀 Casos de Uso Ideais

### ✅ Quando Usar
- **Aplicações desktop** (Electron)
- **Prototipagem rápida**
- **Aplicações mobile** (React Native)
- **Sistemas embarcados**
- **CI/CD e ambientes de teste**
- **Aplicações de pequeno/médio porte**

### ❌ Quando Evitar
- **Alta concorrência** de escritas
- **Aplicações distribuídas**
- **Grandes volumes** com múltiplas transações

---

## 3. 🛠 Implementação Prática

### Instalação e Configuração
```bash
npm install sqlite3
# ou para versão mais moderna
npm install better-sqlite3
```

### Conexão com o Banco
```javascript
// Usando sqlite3
const sqlite3 = require('sqlite3').verbose();
const db = new sqlite3.Database('./database.db', (err) => {
    if (err) {
        console.error('Erro ao conectar:', err.message);
    }
    console.log('Conectado ao SQLite!');
});

// Usando better-sqlite3 (síncrono e mais rápido)
const Database = require('better-sqlite3');
const db = new Database('database.db');
```

### Operações CRUD
```javascript
// Criando tabela
db.run(`
    CREATE TABLE IF NOT EXISTS users (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        name TEXT NOT NULL,
        email TEXT UNIQUE,
        created_at DATETIME DEFAULT CURRENT_TIMESTAMP
    )
`);

// Inserindo dados
const stmt = db.prepare('INSERT INTO users (name, email) VALUES (?, ?)');
stmt.run('João Silva', 'joao@email.com');

// Consultando dados
const users = db.prepare('SELECT * FROM users').all();
console.log(users);
```

---

## 4. 📊 Exemplo Completo: API REST

```javascript
const express = require('express');
const Database = require('better-sqlite3');
const app = express();
const db = new Database('app.db');

app.use(express.json());

// Inicialização do banco
db.exec(`
    CREATE TABLE IF NOT EXISTS tasks (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        title TEXT NOT NULL,
        completed BOOLEAN DEFAULT FALSE,
        created_at DATETIME DEFAULT CURRENT_TIMESTAMP
    )
`);

// Rotas da API
app.get('/tasks', (req, res) => {
    const tasks = db.prepare('SELECT * FROM tasks').all();
    res.json(tasks);
});

app.post('/tasks', (req, res) => {
    const { title } = req.body;
    const stmt = db.prepare('INSERT INTO tasks (title) VALUES (?)');
    const result = stmt.run(title);
    res.json({ id: result.lastInsertRowid, title, completed: false });
});

app.listen(3000, () => {
    console.log('Servidor rodando na porta 3000');
});
```

---

## 5. ⚡ Performance & Boas Práticas

### Otimizações
```javascript
// 1. Usar prepared statements
const stmt = db.prepare('INSERT INTO users (name) VALUES (?)');

// 2. Transações para múltiplas operações
const insertMany = db.transaction((users) => {
    for (const user of users) {
        stmt.run(user.name);
    }
});

// 3. WAL Mode para melhor concorrência
db.pragma('journal_mode = WAL');
```

### Migrações
```javascript
// migrations/001_create_users.js
const db = require('../database');

module.exports = {
    up: () => {
        db.exec(`
            CREATE TABLE users (
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                name TEXT NOT NULL
            )
        `);
    },
    down: () => {
        db.exec('DROP TABLE users');
    }
};
```

---

## 6. 🆚 Comparação: SQLite vs Outras Opções

| Característica | SQLite | PostgreSQL | MySQL |
|----------------|---------|-------------|--------|
| **Configuração** | Zero | Complexa | Moderada |
| **Performance** | ⭐⭐⭐⭐☆ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐☆ |
| **Escalabilidade** | ⭐⭐☆☆☆ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐☆ |
| **Uso em Produção** | Limitado | Ideal | Ideal |

---

## 7. 🔧 Ferramentas Úteis

### GUI Managers
- **DB Browser for SQLite** - Interface gráfica gratuita
- **SQLite Studio** - Alternativa open source
- **VS Code Extensions** - SQLite plugins

### Bibliotecas Populares
```javascript
// Opções para Node.js
const sqlite3 = require('sqlite3');        // Tradicional
const better-sqlite3 = require('better-sqlite3'); // Síncrono + rápido
const knex = require('knex');              // Query Builder
```

---

## 8. 🎯 Conclusão

### Vantagens
- ✅ **Rápido setup** e desenvolvimento
- ✅ **Zero overhead** de administração
- ✅ **Portável** - fácil backup e deploy
- ✅ **Ideal para** projetos pequenos/médios

### Considerações
- 📍 **Entender limitações** de concorrência
- 📍 **Escolher casos de uso** apropriados
- 📍 **Planejar migração** se necessário

---

## 9. 🚀 Próximos Passos

### Hands-on Sugerido
1. Criar uma API REST completa
2. Implementar sistema de migrações
3. Adicionar testes com banco em memória
4. Explorar otimizações de performance

### Recursos
- [Documentação SQLite](https://sqlite.org/docs.html)
- [Node.js SQLite3](https://github.com/TryGhost/node-sqlite3)
- [Better-SQLite3](https://github.com/JoshuaWise/better-sqlite3)

---

**✨ A combinação Node.js + SQLite oferece agilidade incomparável para protótipos e aplicações de pequeno porte!**

---

*Apresentação em Markdown - Pronta para uso!*