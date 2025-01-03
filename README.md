CRUD em Go 🛠️

Este projeto é um exemplo de implementação de um CRUD (Create, Read, Update, Delete) utilizando a linguagem Go, o framework Gorilla Mux para roteamento e MySQL como banco de dados. Ele foi desenvolvido como parte do curso "Aprenda Golang do Zero! Desenvolva uma APLICAÇÃO COMPLETA!" ministrado por Otavio Gallego, com foco no aprendizado de Go e no desenvolvimento de aplicações completas.

🌟 Estrutura do Projeto

main.go: Arquivo principal que inicia o servidor e define as rotas.

servidor/: Contém as funções responsáveis por manipular as requisições HTTP.

bancoDeDados/: Contém a lógica de conexão com o banco de dados.

✅ Pré-requisitos

Certifique-se de ter instalado em sua máquina:

Go (versão 1.16 ou superior)

MySQL

Gorilla Mux

MySQL Driver para Go

🗂️ Configuração do Banco de Dados

Crie um banco de dados chamado devbook no MySQL e adicione a tabela usuarios com a seguinte estrutura:

CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL
);

Certifique-se de que o usuário e senha do banco de dados estão corretos no arquivo bancoDeDados/bancoDeDados.go. A string de conexão está configurada como:

"root@/devbook?charset=utf8&parseTime=True&loc=Local"

🚀 Como Executar

Clone este repositório:

git clone git@github.com:omathcampos/CrudBasico.git

Navegue até o diretório do projeto:

cd CrudBasico

Instale as dependências:

go mod tidy

Inicie o servidor:

go run main.go

O servidor será iniciado na porta 8080.

🌐 Rotas da API

POST /cadastrar-usuario ➡️ Cadastra um novo usuário no banco de dados.

Corpo da requisição (JSON):

{
  "nome": "Nome do Usuário",
  "email": "email@exemplo.com"
}

GET /buscar-usuarios ➡️ Retorna uma lista de todos os usuários.

GET /buscar-usuario/{id} ➡️ Retorna os dados de um usuário específico.

PUT /alterar-usuario/{id} ➡️ Atualiza os dados de um usuário.

Corpo da requisição (JSON):

{
  "nome": "Novo Nome",
  "email": "novoemail@exemplo.com"
}

DELETE /deletar-usuario/{id} ➡️ Remove um usuário do banco de dados.

📦 Dependências

As principais bibliotecas utilizadas neste projeto são:

Gorilla Mux: Framework para roteamento.

MySQL Driver: Driver para conexão com MySQL.
