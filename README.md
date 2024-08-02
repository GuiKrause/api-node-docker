# Projeto de API Simples em Node.js com Docker

## Descrição do Projeto

Este projeto consiste em uma API simples desenvolvida em Node.js, com o objetivo de testar a tecnologia Docker. O projeto inclui um Dockerfile para facilitar a criação de um container Docker, permitindo a execução da aplicação de forma isolada e consistente em qualquer ambiente.

## Aplicação em Execução

![Resposta da API](./images/Screenshot%202024-08-02%20at%2010.24.52.png)

## Propósito da Aplicação

O propósito desta aplicação é meramente educacional apenas com o intuito de demonstrar a criação de uma imagem docker e como executar.

## Estrutura do Projeto

- **`.dockerognore`**: Contém os arquivos ignorados pelo docker.
- **`.gitignore`**: Contém os arquivos ignorados pelo git.
- **`Dockerfile`**: Arquivo de configuração para criação da imagem Docker.
- **`package.json`**: Arquivo de configuração do npm, incluindo dependências e scripts da aplicação.
- **`server.js`**: Entrypoint da aplicação, onde está a importação do express e a única rota do sistema.

## Instruções para Execução

### Requisitos

- [Docker](https://www.docker.com/get-started) instalado no sistema.

### Passos para Executar a Aplicação com Docker

1. **Baixar a imagem docker**

   ```sh
   docker pull krauzzer/api-node-docker:1.0

2. **Subir container**

    ```sh
    Executar o comando:
    docker run -d -p 3000:3000 krauzzer/api-node-docker:1.0

3. **Acessar link**

    ```sh
    A aplicação estará disponível em:
    http://localhost:3000/

## Link para DockerHub

https://hub.docker.com/repository/docker/krauzzer/api-node-docker/general

## Dockerfile

O `Dockerfile` utilizado para criar a imagem Docker da aplicação contém as seguintes instruções:

```dockerfile
FROM node:latest
WORKDIR /app
COPY . .
RUN npm install
ENTRYPOINT npm start
