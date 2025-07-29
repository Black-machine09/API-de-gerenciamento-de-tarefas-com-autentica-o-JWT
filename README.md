# 🗂️ Task Manager API

API RESTful desenvolvida em Django + Django REST Framework para gerenciar tarefas, com autenticação segura via JWT.
Este projeto foi desenvolvido como **teste técnico**, com foco em habilidades de back-end, modelagem de usuários, autenticação e organização de código limpo.

---

## 🚀 Funcionalidades

* 📌 CRUD de tarefas
* 🔐 Autenticação via JWT (Login / Registro)
* 👥 Sistema de usuários customizado
* 🕹️ Filtro por usuário autenticado
* 📅 Datas de vencimento para tarefas
* ⚙️ API protegida por permissão (usuário só acessa seus próprios dados)

---

## 🧪 Tecnologias Utilizadas

* 🐍 Python 3.10+
* 🌐 Django 4.x
* 🔧 Django REST Framework
* 🛡️ Simple JWT
* 💾 SQLite3 (compatível com PostgreSQL)

---

## 🔧 Como executar o projeto localmente

### 1. Clone o repositório

```bash
git clone https://github.com/Black-machine09/API-de-gerenciamento-de-tarefas-com-autentica-o-JWT.git
cd API-de-gerenciamento-de-tarefas-com-autentica-o-JWT
```

### 2. Crie um ambiente virtual (opcional, mas recomendado)

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Realize as migrações

```bash
python manage.py migrate
```

### 5. Crie um superusuário

```bash
python manage.py createsuperuser
```

### 6. Execute o servidor

```bash
python manage.py runserver
```

Acesse em: [http://localhost:8000](http://localhost:8000)

---

## 🧪 Exemplos de uso da API (via cURL ou Postman)

### 🔐 Autenticação - Login

```http
POST /api/token/
{
  "email": "seuemail@exemplo.com",
  "password": "suasenha"
}
```

### 📌 Criar Tarefa

```http
POST /api/tasks/
Authorization: Bearer <SEU_TOKEN_AQUI>
{
  "titulo": "Exemplo de tarefa",
  "descricao": "Esta é uma tarefa de exemplo",
  "data_vencimento": "2025-08-01"
}
```

### 🗑️ Deletar Tarefa

```http
DELETE /api/tasks/1/
Authorization: Bearer <SEU_TOKEN_AQUI>
```

---

## 📁 Estrutura de diretórios

```bash
.
├── manage.py
├── requirements.txt
├── README.md
├── users/         
└── tasks/           

---

## 📌 Observações

* A autenticação é obrigatória para qualquer requisição nas rotas protegidas.
* JWT Access Tokens expiram após um tempo. Para renová-lo, use `/api/token/refresh/`.
* As tarefas são sempre filtradas por usuário autenticado.
