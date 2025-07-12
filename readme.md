# Let Me Ask

Sistema completo para criação de salas de perguntas e respostas com suporte a transcrição de áudio e geração de respostas por Inteligência Artificial (IA).

## Funcionalidades

- **Criação de salas:** Crie salas temáticas para perguntas e respostas.
- **Envio de perguntas:** Envie perguntas escritas para a IA responder.
- **Gravação de áudio:** Grave e envie áudios para serem transcritos e usados como contexto nas respostas.
- **Respostas inteligentes:** As respostas são geradas pela IA Gemini, utilizando o contexto das transcrições de áudio.
- **Listagem de salas e perguntas:** Visualize salas recentes e perguntas/respostas em tempo real.

## Tecnologias Utilizadas

- **Frontend:** React, Vite, TailwindCSS, React Query, Zod, Radix UI, Lucide Icons
- **Backend:** Fastify, Drizzle ORM, PostgreSQL (com extensão pgvector), Google Gemini API
- **Banco de Dados:** PostgreSQL com suporte a vetores para embeddings
- **Dev Tools:** TypeScript, Biome, Drizzle Kit, Docker

## Como Executar

### Pré-requisitos

- Node.js >= 18
- Docker (para banco de dados)
- Chave da API Gemini (Google GenAI)

### Backend

1. **Configurar variáveis de ambiente:**
   - Copie `.env.example` para `.env` e preencha `DATABASE_URL` e `GEMINI_API_KEY` com suas informações.

2. **Subir banco de dados:**
   ```sh
   cd server
   docker compose up -d
   ```

3. **Executar migrações e seed:**
   ```sh
   npm run db:migrate
   npm run db:seed
   ```

4. **Iniciar servidor:**
   ```sh
   npm run dev
   ```

### Frontend

1. **Instalar dependências:**
   ```sh
   cd web
   npm install
   ```

2. **Iniciar aplicação:**
   ```sh
   npm run dev
   ```

3. **Acesse:** [http://localhost:5173](http://localhost:5173)

## API

- **GET /rooms:** Lista todas as salas
- **POST /rooms:** Cria uma nova sala
- **GET /rooms/:roomId/questions:** Lista perguntas de uma sala
- **POST /rooms/:roomId/questions:** Cria uma pergunta
- **POST /rooms/:roomId/audio:** Envia áudio para transcrição

Veja exemplos em `server/client.http`.

## Contribuição

1. Fork este repositório
2. Crie uma branch: `git checkout -b minha-feature`
3. Commit suas alterações: `git commit -m 'Minha feature'`
4. Push para o branch: `git push origin minha-feature`
5. Abra um Pull Request