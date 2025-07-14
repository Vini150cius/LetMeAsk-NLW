# LetMeAsk - NLW

\<img src="./LogoLetMeAsk-NLW.jpg" alt="Logo do projeto"\>

> Projeto de uma aplicação que fornece respostas de acordo com o que for dito em um áudio ou vídeo.

-----

## ➕ Explicação detalhada do projeto

Projeto desenvolvido durante um evento da Rocketseat para demonstrar o uso de agentes inteligentes na web. Inicialmente, permite que o usuário grave um áudio e faça perguntas sobre o conteúdo, podendo ser utilizado em cursos ou livestreams. Um usuário fornecerá o áudio para a plataforma e outros usuários poderão fazer qualquer pergunta que desejarem sobre o conteúdo, e a I.A. tentará responder com base na aula ministrada.

Nesse projeto, foram trabalhadas algumas tecnologias e, principalmente, como ter uma **API Rest**, abordando a comunicação da API com um banco de dados e a comunicação do front-end com a API.

-----

## 🔧 Tecnologias utilizadas

### Web - Front-end

  - **React** - Biblioteca para interfaces de usuário
  - **TypeScript** - Superset JavaScript com tipagem estática
  - **Vite** - Build tool e servidor de desenvolvimento
  - **TailwindCSS** - Framework CSS utility-first
  - **Shadcn/ui** - Sistema de componentes
  - **Lucide React** - Biblioteca de ícones

### Server - Back-end

  - **Node.js** com TypeScript nativo
  - **Fastify** - Framework web rápido e eficiente
  - **PostgreSQL** com extensão **pgvector** para vetores
  - **Drizzle ORM** - Type-safe database operations
  - **Zod** - Schema validation
  - **Docker** - Containerização do banco de dados
  - **Biome** - Linting e formatação de código

-----

### Ajustes e melhorias

Planejo realizar aprimoramentos no projeto para ter características próprias e se tornar uma plataforma mais completa:

  - Adicionar login de usuários, para que fique explícito quem fez qual pergunta e quem fez o upload do áudio.
  - Aprimorar a tela de captura de áudio.
  - Permitir que o usuário suba vídeos, para que a plataforma converta em áudio e forneça respostas.
  - Verificar a viabilidade de permitir que o usuário forneça apenas um link do YouTube e a plataforma já pegue o conteúdo para permitir perguntas sobre aquele vídeo.
  - Adicionar uma verificação de conteúdo nas mensagens.

-----

# 🚀 Instalando os arquivos do LetMeAsk - NLW

Como o projeto é separado em "web" e "server", é preciso primeiro instalar as dependências do servidor e iniciá-lo, e depois instalar e iniciar a parte web.

### Clone o repositório

```bash
git clone https://github.com/Vini150cius/LetMeAsk-NLW.git
cd letmeask-nlw
```

-----

## Server

### 1\. Entrar na pasta

```bash
cd server
```

### 2\. Configure o banco de dados

```bash
docker-compose up -d
```

### 3\. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
GEMINI_API_KEY="SUA CHAVE"
```

### 4\. Instale as dependências

```bash
npm i
```

### 5\. Execute as migrações do banco

```bash
npx drizzle-kit migrate
```

### 6\. (Opcional) Popule o banco com dados de exemplo

```bash
npm run db:seed
```

### 7\. Execute o projeto

**Desenvolvimento:**

```bash
npm run dev
```

**Produção:**

```bash
npm start
```

-----

## Web

```bash
cd web
npm run dev
```

-----

## 📝 Licença

O projeto pode ser usado para estudo ou até mesmo reciclado para algum outro projeto, mas caso for utilizar, peço encarecidamente para dar o devido crédito.

-----

# 📖 Anotações

## Comandos do Docker no terminal

```shell
docker ps
```

> Lista os containers Docker que estão rodando.

```shell
docker ps -a
```

> Lista todos os containers Docker.

```shell
docker compose up -d
```

> Ele constrói seu Docker e o `-d` serve para deixar o terminal disponível para outros comandos.

-----

## Drizzle

Serve para criar o banco de dados de uma forma mais facilitada. Você monta o schema, executa e ele já cria o que você pediu.

```shell
npm i drizzle-orm
npm i drizzle-kit -D
```

> Comandos de instalação.

```shell
npx drizzle-kit generate
```

> Gera um arquivo SQL com o que foi montado. É importante antes configurar o `drizzle.config.ts`.

```shell
npx drizzle-kit migrate
```

```shell
npx drizzle-kit studio
```

> Fornece uma URL para você visualizar seu banco de dados, as tabelas e tudo mais.