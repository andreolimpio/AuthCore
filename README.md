# 🔐 AuthCore

**Sistema de Autenticação, Gerenciamento de Usuários e Controle de Acesso**

O **AuthCore** é uma aplicação Web Full Stack desenvolvida para implementar, de forma organizada e segura, os principais recursos relacionados à autenticação e ao gerenciamento de usuários em sistemas modernos.

O projeto utiliza uma arquitetura em camadas, separando claramente as responsabilidades entre **Frontend, API, regras de negócio, acesso aos dados e banco de dados**.

Além de funcionar como uma aplicação independente, o AuthCore foi projetado para servir como uma **base reutilizável de autenticação e controle de acesso**, podendo futuramente ser integrado a outros sistemas Web, aplicações Mobile, APIs e projetos acadêmicos.

---

## 🎯 Objetivo do Projeto

O objetivo principal do AuthCore é desenvolver uma aplicação completa para gerenciamento e autenticação de usuários, aplicando conceitos de desenvolvimento **Frontend, Backend, APIs REST, Banco de Dados, Segurança e Engenharia de Software**.

O projeto também busca demonstrar, na prática, como diferentes tecnologias trabalham de maneira integrada dentro de uma aplicação Full Stack.

---

## 🧩 Principais Funcionalidades

O sistema deverá permitir:

- Autenticação de usuários por login e senha;
- Cadastro de novos usuários;
- Consulta e listagem de usuários cadastrados;
- Atualização dos dados de usuários;
- Desativação de usuários por meio de Soft Delete;
- Alteração da própria senha pelo usuário autenticado;
- Armazenamento seguro de senhas utilizando hash;
- Controle do status da conta;
- Registro da quantidade de acessos realizados;
- Registro da data e hora do último acesso;
- Registro de tentativas e/ou acessos ao sistema;
- Proteção de recursos que exigem autenticação.

---

## 🏗️ Arquitetura

O AuthCore utiliza uma arquitetura em camadas para separar responsabilidades e facilitar a organização, manutenção e evolução do sistema.

Fluxo principal da aplicação:

Frontend
↓
API REST
↓
Routes
↓
Controllers
↓
Services
↓
Repositories
↓
MySQL

### Frontend

Responsável pela interface e interação com o usuário.

Tecnologias:

- HTML5
- CSS3
- JavaScript
- TypeScript
- Fetch API

### Backend

Responsável pelo processamento das requisições, regras de negócio, autenticação e comunicação com o banco de dados.

Tecnologias:

- Node.js
- Express
- TypeScript

### Banco de Dados

O armazenamento persistente dos dados será realizado utilizando:

- MySQL
- Driver MySQL2
- Connection Pool
- Prepared Statements

---

## 📁 Estrutura Inicial do Projeto

authcore/
│
├── frontend/
│   ├── pages/
│   ├── css/
│   ├── js/
│   └── assets/
│
├── backend/
│   └── src/
│       ├── config/
│       ├── controllers/
│       ├── services/
│       ├── repositories/
│       ├── models/
│       ├── dto/
│       ├── routes/
│       ├── middlewares/
│       └── utils/
│
├── database/
│   ├── create_database.sql
│   ├── create_tables.sql
│   └── seed.sql
│
├── docs/
│   ├── arquitetura/
│   ├── banco-de-dados/
│   ├── api/
│   └── imagens/
│
├── .env.example
├── .gitignore
├── LICENSE
└── README.md

---

## 🗄️ Banco de Dados

A tabela principal do sistema será responsável pelo armazenamento dos usuários.

### usuarios

Principais atributos:

- `id_usuario`
- `login`
- `senha_hash`
- `nome`
- `data_cadastro`
- `data_atualizacao`
- `ultimo_acesso`
- `status`
- `quantidade_acessos`

O projeto também poderá utilizar uma tabela específica para registro dos acessos realizados ao sistema.

### logs_acesso

Exemplos de atributos:

- `id_log`
- `id_usuario`
- `data_hora`
- `ip`
- `resultado`

---

## 🔒 Segurança

O AuthCore será desenvolvido considerando boas práticas de segurança para aplicações Web.

Entre elas:

- Senhas armazenadas utilizando algoritmo adequado de hash;
- Salt para proteção das credenciais;
- Autenticação baseada em token ou sessão segura;
- Middleware de autenticação;
- Controle de acesso aos endpoints protegidos;
- Prepared Statements;
- Proteção contra SQL Injection;
- Validação dos dados recebidos pela API;
- Variáveis de ambiente para informações sensíveis;
- Controle de usuários por status;
- Registro de acessos ao sistema.

> Senhas nunca deverão ser armazenadas em texto puro no banco de dados.

---

## 🔄 Soft Delete

A exclusão de usuários será realizada utilizando o conceito de **Soft Delete**.

Dessa forma, o registro não será removido fisicamente do banco de dados.

Em vez de executar:

DELETE FROM usuarios

o sistema atualizará o status do usuário, por exemplo:

UPDATE usuarios
SET status = 'INATIVO'
WHERE id_usuario = ?;

Essa abordagem permite preservar o histórico e a integridade dos dados.

---

## 🌐 API REST

A comunicação entre Frontend e Backend será realizada por meio de uma API REST utilizando HTTP/HTTPS e JSON.

Exemplos de endpoints previstos:

POST /api/auth/login

POST /api/users

GET /api/users

GET /api/users/:id

PUT /api/users/:id

PATCH /api/users/:id/status

PATCH /api/users/me/password

Os endpoints poderão ser ampliados durante a evolução do projeto.

---

## 🛠️ Tecnologias

| Tecnologia | Aplicação |
|---|---|
| HTML5 | Estrutura das interfaces |
| CSS3 | Estilização |
| JavaScript | Interatividade no Frontend |
| TypeScript | Desenvolvimento tipado |
| Node.js | Ambiente Backend |
| Express | API e servidor HTTP |
| MySQL | Banco de dados relacional |
| MySQL2 | Comunicação Node.js/MySQL |
| Git | Controle de versão |
| GitHub | Repositório e documentação |

---

## 📚 Conceitos Aplicados

Durante o desenvolvimento serão trabalhados conceitos relacionados a:

- Desenvolvimento Full Stack;
- Arquitetura em camadas;
- Cliente e servidor;
- Frontend e Backend;
- API REST;
- Métodos HTTP;
- JSON;
- CRUD;
- Autenticação;
- Autorização;
- Hash de senhas;
- Middlewares;
- DTOs;
- Models;
- Services;
- Repositories;
- Banco de dados relacional;
- SQL;
- Prepared Statements;
- Segurança de aplicações Web;
- Git e GitHub;
- Documentação de software.

---

## 🚀 Evolução do Projeto

O AuthCore foi projetado para ser evolutivo.

Versões futuras poderão incluir:

- Perfis de usuário;
- Papéis e permissões;
- Recuperação de senha;
- Confirmação de e-mail;
- Autenticação multifator;
- Controle de sessões;
- Dashboard administrativo;
- Histórico de alterações;
- Auditoria;
- Integração com aplicações Mobile;
- Integração com outros sistemas e APIs.

Dessa maneira, o AuthCore poderá funcionar como um módulo de identidade e autenticação reutilizável em diferentes aplicações.

---

## 📖 Documentação

A documentação do projeto será mantida no próprio repositório, incluindo:

- Arquitetura da aplicação;
- Modelo do banco de dados;
- Dicionário de dados;
- Scripts SQL;
- Documentação da API;
- Requisitos funcionais e não funcionais;
- Diagramas;
- Instruções de instalação;
- Histórico de evolução do projeto.

---

## 🧪 Status do Projeto

🚧 **Em desenvolvimento**

O projeto será construído de forma incremental, com novas funcionalidades e melhorias adicionadas ao longo das próximas versões.

---

## 👨‍💻 Desenvolvimento

Projeto desenvolvido para fins educacionais, acadêmicos e de experimentação prática em desenvolvimento de software Full Stack.

O objetivo é aproximar conceitos teóricos de situações encontradas no desenvolvimento de aplicações reais, incentivando boas práticas de programação, arquitetura, segurança, documentação e versionamento.

---

## 📄 Licença

A licença de utilização e distribuição do projeto será definida de acordo com sua finalidade acadêmica e educacional.

---

### AuthCore

**Uma base de autenticação. Múltiplas possibilidades de aplicação.**
