# 🖥️  Projeto Backend + SQL - PHP 

> Projeto acadêmico desenvolvido durante o curso de **Desenvolvimento de Sistemas — SENAI**.

## 📌 Sobre o projeto

Este projeto consiste na criação de um servidor utilizando **PHP**, integrado a um banco de dados **PostgreSQL**.

A aplicação funciona como uma API simples para gerenciamento de produtos, permitindo cadastrar e consultar informações por meio de requisições HTTP.

Os dados são enviados e recebidos no formato **JSON**, e a comunicação com o banco de dados é realizada utilizando **PDO**.

## ⚙️ Funcionalidades

* 📦 Cadastro de produtos;
* 🔎 Consulta de produtos cadastrados;
* 🗄️ Integração com PostgreSQL;
* 🔗 Conexão com banco utilizando PDO;
* 📄 Recebimento de dados em JSON;
* 📤 Retorno de dados em JSON;
* 🌐 Utilização dos métodos HTTP `GET` e `POST`.

## 🛠️ Tecnologias utilizadas

* **PHP**
* **PostgreSQL**
* **PDO**
* **JSON**
* **HTTP**
* **Python**
* **Biblioteca Requests**
* **API ViaCEP**

## 📂 Estrutura do projeto

```text
servidor/
├── .gitignore
├── index.php
├── teste.py
└── README.md
```

> O arquivo `conexao.php` não está no repositório, pois foi incluído no `.gitignore` para proteger as informações de acesso ao banco de dados.

## 🔌 API de Produtos

### 📥 POST — Cadastrar produto

Utilizado para cadastrar um novo produto no banco de dados.

**Exemplo de requisição:**

```http
POST /
Content-Type: application/json
```

**Dados enviados:**

```json
{
    "nome": "Caderno",
    "preco": 25.90
}
```

**Resposta:**

```json
{
    "Mensagem": "Produto cadastrado com sucesso!✅"
}
```

### 📤 GET — Consultar produtos

Utilizado para consultar os produtos cadastrados no banco de dados.

**Exemplo de requisição:**

```http
GET /
```

**Exemplo de resposta:**

```json
[
    {
        "id": 1,
        "nome": "Caderno",
        "preco": "25.90"
    },
    {
        "id": 2,
        "nome": "Caneta",
        "preco": "3.50"
    }
]
```

## 🗄️ Banco de dados

O projeto utiliza o **PostgreSQL** para armazenar os produtos.

A tabela `produtos` possui os seguintes campos:

| Campo   | Descrição                |
| ------- | ------------------------ |
| `id`    | Identificador do produto |
| `nome`  | Nome do produto          |
| `preco` | Preço do produto         |

### Estrutura da tabela

```sql
CREATE TABLE produtos (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    preco DECIMAL(10,2) NOT NULL
);
```

## 🔄 Funcionamento da API

```text
Cliente
   │
   │ Requisição HTTP
   ▼
Servidor PHP
   │
   ├── POST → Cadastra produto
   │
   └── GET → Consulta produtos
   │
   ▼
PostgreSQL
   │
   ▼
Resposta em JSON
```

## 🧪 Teste com API externa

Durante a atividade, também foi realizado um teste utilizando **Python** e a API pública **ViaCEP**.

O programa recebe um CEP informado pelo usuário, realiza uma requisição HTTP e utiliza os dados retornados em formato JSON para exibir as informações do endereço.

### 🔹 Funcionamento

```text
CEP informado pelo usuário
          ↓
Requisição HTTP para o ViaCEP
          ↓
Dados retornados em JSON
          ↓
Informações do endereço
          ↓
Exibição no terminal
```

### 🐍 Tecnologias utilizadas no teste

* Python
* Biblioteca `requests`
* API ViaCEP
* JSON
* Requisições HTTP

### 📌 Exemplo

```text
Digite o seu CEP: 13465-000

Você mora na Rua ... no bairro ... na cidade Americana
no estado de SP na região Sudeste
```

O teste teve como objetivo praticar o **consumo de APIs externas**, realizando requisições e trabalhando com os dados recebidos em JSON.

## 🎯 Objetivos da atividade

A atividade teve como objetivo colocar em prática conceitos de:

* Desenvolvimento de servidores;
* APIs;
* Requisições HTTP;
* PHP;
* PostgreSQL;
* PDO;
* JSON;
* Consumo de APIs externas;
* Python.

## 🔐 Segurança

O arquivo `conexao.php` foi adicionado ao `.gitignore` porque contém informações utilizadas para realizar a conexão com o banco de dados.

Em projetos reais, informações sensíveis como senhas e credenciais devem ser protegidas e não devem ser publicadas em repositórios públicos.

## 👩‍💻 Projeto acadêmico

**Curso:** Desenvolvimento de Sistemas
**Instituição:** SENAI

---

⭐ Projeto desenvolvido para fins acadêmicos e de aprendizado.
