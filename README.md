# 🚀 Projeto CRUD de Usuários em Go

Este é um projeto simples que implementa um CRUD (Create, Read, Update, Delete) para gerenciamento de usuários utilizando Go e MySQL. O projeto foi incentivado e feito durante o curso "Aprenda Golang do Zero! Desenvolva uma APLICAÇÃO COMPLETA!" do Otávio Gallego.

## 🧑‍💻 Funcionalidades

- ✨ **Criar usuário**: Cadastrar um novo usuário no banco de dados.
- 🔍 **Buscar usuários**: Retornar a lista de todos os usuários cadastrados.
- 👤 **Buscar usuário por ID**: Buscar um usuário específico pelo seu ID.
- ✏️ **Atualizar usuário**: Alterar as informações de um usuário existente.
- ❌ **Deletar usuário**: Deletar um usuário pelo seu ID.

## 🛠️ Tecnologias Utilizadas

- **Go**: Linguagem de programação principal para o desenvolvimento da aplicação.
- **MySQL**: Banco de dados utilizado para armazenar os dados dos usuários.
- **Gorilla Mux**: Biblioteca para roteamento de HTTP em Go.
- **JSON**: Formato para troca de dados entre a API e o cliente.

## 📂 Estrutura do Projeto

- `main.go`: Arquivo principal onde o servidor HTTP é configurado e as rotas da API são definidas.
- `servidor/servidor.go`: Arquivo contendo as funções responsáveis pelas operações CRUD.
- `bancoDeDados/bancoDeDados.go`: Arquivo com a função de conexão com o banco de dados MySQL.

## 🌍 Endpoints da API

### 1. 🆕 Criar Usuário

- **Método**: POST
- **Endpoint**: `/cadastrar-usuario`
- **Descrição**: Cria um novo usuário no banco de dados.
- **Body (JSON)**:
  ```json
  {
    "nome": "Nome do Usuário",
    "email": "email@dominio.com"
  }

### 2. 📜 Buscar Todos os Usuários

- **Método**: GET
- **Endpoint**: `/buscar-usuarios`
- **Descrição**: Retorna uma lista de todos os usuários cadastrados.

### 3. 🔍 Buscar Usuário por ID

- **Método**: GET
- **Endpoint**: `/buscar-usuario/{id}`
- **Descrição**: Retorna os dados de um usuário específico pelo ID.
- **Parâmetro**: `{id}` - ID do usuário.

### 4. ✏️ Atualizar Usuário

- **Método**: PUT
- **Endpoint**: `/alterar-usuario/{id}`
- **Descrição**: Atualiza as informações de um usuário específico.
- **Parâmetro**: `{id}` - ID do usuário.
- **Body (JSON)**:
  ```json
  {
    "nome": "Novo Nome",
    "email": "novoemail@dominio.com"
  }

### 5. ❌ Deletar Usuário

- **Método**: DELETE
- **Endpoint**: `/deletar-usuario/{id}`
- **Descrição**: Deleta um usuário pelo ID.
- **Parâmetro**: `{id}` - ID do usuário.

## 🔧 Instalação

```bash
### 1. Clone o Repositório

git clone git@github.com:omathcampos/CrudBasico.git

### 2. Instale as Dependências

Em vez de instalar as dependências manualmente, use o comando abaixo para garantir que todas as dependências necessárias sejam baixadas:

go mod tidy

### 3. Configure o Banco de Dados

Crie um banco de dados MySQL chamado `devbook` e configure os detalhes da conexão no arquivo `bancoDeDados.go`.

stringConexaoSQL := "root@/devbook?charset=utf8&parseTime=True&loc=Local"

### 4. Execute o Projeto

Para rodar o servidor, basta executar:

go run main.go

