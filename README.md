# API Project

API simples em Node.js + TypeScript para listar e filtrar episódios de podcast.

## Descrição

Esta aplicação expõe uma API HTTP minimalista (sem frameworks) que permite:

- Listar episódios disponíveis
- Filtrar episódios por nome (query string)

## Tecnologias

- Node.js
- TypeScript
- tsx (execução em desenvolvimento)
- tsup (build)

## Estrutura do projeto

- `src/` — código fonte
  - `app.ts` — roteamento principal
  - `server.ts` — inicialização do servidor
  - `controllers/` — controladores HTTP
  - `services/` — lógica de negócio
  - `repositories/` — acesso a dados (arquivo `podcasts.json`)
  - `routes/` — definição das rotas
  - `models/`, `utils/` — modelos e utilitários

## Instalação

1. Instale as dependências:

```bash
npm install
```

2. Crie um arquivo `.env` na raiz com a variável `PORT` (ex.: `PORT=3000`).

## Execução

- Modo desenvolvimento:

```bash
npm run start:dev
```

- Modo com watch:

```bash
npm run start:watch
```

- Build/produção (gerar bundle e iniciar):

```bash
npm run dist
npm run start:dist
```

> Observação: os scripts disponíveis estão no `package.json`.

## Endpoints

- `GET /api/list` — retorna a lista completa de episódios.
- `GET /api/episode?p=<termo>` — filtra episódios pelo termo passado em `p`.

Exemplo de uso:

```bash
# listar todos
curl http://localhost:3000/api/list

# filtrar por nome
curl "http://localhost:3000/api/episode?p=nome-do-podcast"
```

### 🎙️ Podcasts Disponíveis (Valores válidos para `podcastName`)

- `flow`
- `podpah`
- `inteligencia_ltda`
- `ciencia_sem_fim`
- `primocast`
- `ironberg`
- `ticaracaticast`
- `venus`