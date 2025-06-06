---
theme: default
lineNumbers: true
layout: cover
title: Nodejs + MongoDB
author: José Roberto Bezerra
exportFilename: pw1_aula10_node_mdb
colorSchema: dark
---

# Programação Web 1
Nodejs + MongoDB
<logos-nodejs-icon /> <logos-mongodb-icon />

---

# Objetivo de Aprendizagem
- Aplicar o MongoDB juntamente com Nodejs

---

# Agenda
- `MongoClient`
- *Connection Guide*
- Cursor

---
layout: section
---

# `MongoClient`

---

# *Connection String*

Exemplo de URI de conexão do MongoDB Atlas:

```js
"mongodb+srv://<username>:<password>@<your-cluster-url>/test?retryWrites=true&w=majority"
```

---

# *Connection Options*

- `poolSize=20`: tamanho máximo da instância do pool de conexões
- `w=majority`: nível de confirmação de escrita pela maioria dos servidores
- `<number>`: número específico de servidores a confirmar
- `<custom write concern>`: nome de um servidor específico

[Opções de Conexão - Documentação](https://www.mongodb.com/docs/drivers/node/v3.7/fundamentals/connection/#std-label-connection-options)

---

# *Connection Pool*

- `MongoClient` é a classe básica para conexão com MongoDB
- Cada instância representa um *pool* (conjunto) de conexões
- Mesmo aplicações *multithread* usam apenas uma instância de `MongoClient`

---

# MongoClient - Exemplo

```js
const { MongoClient } = require("mongodb");
const uri = "mongodb+srv://sample-hostname:27017/?maxPoolSize=20&w=majority";
const client = new MongoClient(uri);
```

---

# Testando a Conexão (`checkconn.js`)

```js
async function run() {
  try {
    await client.connect();
    await client.db("admin").command({ ping: 1 });
    console.log("Connected successfully to server");
  } finally {
    await client.close();
  }
}

run().catch(console.dir);
```

---

# Listando BDs (`listdbs.js`)

```js
async function main() {
  const uri = "mongodb+srv://<username>:<password>@<your-cluster-url>/test?retryWrites=true&w=majority";
  const client = new MongoClient(uri);
  try {
    await client.connect();
    await listDatabases(client);
  } catch (e) {
    console.error(e);
  } finally {
    await client.close();
  }
}

main().catch(console.error);
```

---

# Listando BDs - Função Auxiliar

```js
async function listDatabases(client) {
  const databasesList = await client.db().admin().listDatabases();
  console.log("Databases:");
  databasesList.databases.forEach(db => console.log(` - ${db.name}`));
}
```

---

# Sample Data no Atlas

"Atlas provides sample data you can load into your Atlas database deployments."

[Tutorial Sample Data](https://www.mongodb.com/docs/atlas/sample-data/)

---

# Como Carregar Sample Data

1. Acessar o Atlas
2. Clicar em "Database"
3. Clicar nos três pontos (…)
4. Selecionar "Load Sample Dataset"
5. Aguardar alguns minutos
6. Clicar em "Browse Collections"

Exemplos:
- sample_airbnb
- sample_geospatial
- sample_guides
- sample_mflix
- sample_supplies
- sample_training
- sample_weatherdata

---

# Sample Airbnb (`sample_abnb.js`)

```js
async function main() {
  const { MongoClient } = require('mongodb');
  const uri = 'mongodb+srv://<dbUser>:<password>@cluster0.mongodb.net/?retryWrites=true&w=majority';
  const client = new MongoClient(uri);
  await client.connect();
  await findListings(client, 3);
  await client.close();
}
```

---

# Função `findListings`

```js
async function findListings(client, resultsLimit) {
  const cursor = client.db('sample_airbnb')
    .collection('listingsAndReviews')
    .find()
    .limit(resultsLimit);

  const results = await cursor.toArray();

  if (results.length > 0) {
    console.log(`Found ${results.length} listing(s):`);
    results.forEach((result, i) => {
      console.log(`\n${i + 1}. Name: ${result.name}`);
      console.log(`   Bedrooms: ${result.bedrooms}`);
      console.log(`   Bathrooms: ${result.bathrooms}`);
    });
  }
}
```

---

# Cursor

- Permite percorrer o resultado de uma consulta ao BD
- Modifica documentos e campos retornados
- [Operadores de comparação](https://www.mongodb.com/docs/manual/reference/operator/query-comparison/)
- [Métodos do Cursor](https://www.mongodb.com/docs/upcoming/reference/method/js-cursor/)

---

# 


---

# Exercício 1

1. Reproduzir os *scripts* usando seu próprio cluster do Atlas
2. Ajustar a *connection string* usando o módulo Dotenv para evitar a exposição das credenciais de acessso ao MDB no código fonte
3. Carregar as coleções de amostra

---

# Exercício 2 (`checkconnV2.js`)

- Aprimorar a verificação de conexão a partir de `checkconn.js`
- Versão aprimorada para testar se o servidor está ativo
- Mostra os *hosts* do *cluster*
- Exibe mensagens de sucesso ou erro

---

# Exercício 3 (`listdbsV2.js`)

- Baseado no `listdbs.js`
- Versão aprimorada verifica se a consulta foi realizada corretamente
- Exibe a lista de bancos com `sizeOnDisk`
- Mostra o tamanho total do cluster

---

# Exercício 4 (`sample_abnbV2.js`)

- Listar 10 melhores propriedades com:
  - `review_scores_rating >= 80`
  - Campo `name` não vazio
  - Exibir somente: `name`, `listing_url`, `review_scores_rating`

---

# Exercício 5 (`restaurants.js`)

- Criar script para questão 9 da aula anterior usando `restaurants.json`

[Exercícios MongoDB](https://www.w3resource.com/mongodb-exercises/)

---

# Referências

- [Async/Await com Node.js](https://www.freecodecamp.org/news/node-js-async-await-tutorial-with-asynchronous-javascript-examples/)
- [Sample Data - MongoDB Atlas](https://www.mongodb.com/docs/atlas/sample-data/)

---
layout: end
---

# Prof. José Roberto Bezerra
jbroberto@ifce.edu.br
<br><br>
<PoweredBySlidev />