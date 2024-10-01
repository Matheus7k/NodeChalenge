# NodeChalenge

Esta é uma aplicação backend desenvolvida em Node.js com TypeScript, utilizando o framework Koa para gerenciar rotas e middleware. A aplicação é integrada ao AWS Cognito para autenticação de usuários e utiliza TypeORM para gerenciar a persistência de dados em um banco de dados PostgreSQL. O objetivo desta aplicação é fornecer uma API robusta e escalável, facilitando a implementação de funcionalidades relacionadas à autenticação e gerenciamento de usuários.

## Tecnologias

- Node.js
- TypeScript
- Koa
- TypeORM
- AWS Cognito
- PostgreSQL

## Pré-requisitos

Antes de começar, você precisará ter o Node.js e o Docker instalados em sua máquina, além de uma instância do PostgreSQL rodando, seja localmente ou através do Docker.

## Instalação

### Local
Para rodar a aplicação localmente, siga os passos abaixo:

1. Clone este repositório:

   ```bash
   git clone <URL do repositório>
   cd <nome do repositório>
   ```

2. Configurar o PostgreSQL com Docker:
    - Baixe a imagem do PostgreSQL 14:
        ```bash
        docker pull postgres:14
        ```
    - Inicie um container do PostgreSQL:
        ```bash
        docker run --name postgres-container -e POSTGRES_USER=<seu_usuario> -e POSTGRES_PASSWORD=<sua_senha> -e POSTGRES_DB=<seu_banco> -p 5432:5432 -d postgres:14
        ```
    Substitua `<seu_usuario>`, `<sua_senha>`, e `<seu_banco>` pelos valores desejados.

3. Instale as depenências
    ```
    npm install
    ```

4. Adicione as credenciais do Cognito no arquivo .env:
    ```bash
    COGNITO_USER_POOL_ID=<seu_user_pool_id>
    COGNITO_CLIENT_ID=<seu_client_id>
    ```

5. Para iniciar a aplicação em modo de desenvolvimento, execute:
    ```
    npm run dev
    ```

### Docker
Se preferir executar a aplicação usando Docker, siga os passos abaixo:

1. Adicione as mesmas variáveis do Cognito no arquivo docker-compose.yml:

   ```
   environment:
    COGNITO_USER_POOL_ID: <seu_user_pool_id>
    COGNITO_CLIENT_ID: <seu_client_id>
    ```

2. Execute o Docker Compose para construir e iniciar os containers:
    ```
    docker-compose up --build
    ```

# Scripts
- npm run dev: Inicia a aplicação em modo de desenvolvimento.
- docker-compose up --build: Constrói e inicia a aplicação usando Docker.