# Agents

This project is a backend API developed during [Rocketseat NLW](https://rocketseat.com.br/) coding event. The project demonstrates a modern TypeScript stack for building APIs focusing on clean architecture.

## 🚀 Technologies & Libraries Used

- **TypeScript:** Static typing for  JavaScript
- **[Fastify](https://fastify.io/):** High-performance Node.js web framework
- **[Drizzle ORM](https://orm.drizzle.team/):** TypeScript ORM for SQL databases
- **[Zod](https://zod.dev/):** TypeScript-first schema validation
- **[PostgreSQL](https://www.postgresql.org/):** Relational database
- **[fastify-type-provider-zod](https://github.com/fastify/fastify-type-provider-zod):** Zod integration for Fastify
- **[@fastify/cors](https://github.com/fastify/fastify-cors):** CORS support for Fastify
- **[Drizzle Kit](https://kit.drizzle.team):** Database migrations and schema management
- **[Biome](https://biomejs.dev/):** Code formatting and linting

## 📁 Project Structure

```
server/
├── src/
│   ├── db/                # Database connection, schema, and seed scripts
│   │   ├── schema/        # Table definitions (e.g., rooms)
│   │   ├── migrations/    # Database migrations
│   │   ├── connection.ts  # DB connection setup
│   │   └── seed.ts        # Seed script
│   ├── http/
│   │   └── routes/        # API route handlers
│   ├── env.ts             # Environment variable config
│   └── server.ts          # Main server entry point
├── package.json           # Project metadata and scripts
├── drizzle.config.ts      # Drizzle ORM config
├── docker-compose.yml     # Docker setup (if used)
└── client.http            # Example HTTP requests
```

## ⚙️ Setup & Running

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Configure environment variables:**
   - Create a `.env` file with the necessary variables (e.g., `PORT`, `DATABASE_URL`).

3. **Run database migrations:**
   ```bash
   npx drizzle-kit migrate
   ```

4. **Seed the database (optional):**
   ```bash
   npm run db:seed
   ```

5. **Start the development server:**
   ```bash
   npm run dev
   ```

   The server will start on the port specified in your `.env` file (default: 3333).

## 📚 API Endpoints

### `GET /health`
- **Description:** Health check endpoint.
- **Response:**
  ```json
  { "status": "OK" }
  ```

### `GET /rooms`
- **Description:** Returns a list of all rooms.
- **Response:**
  ```json
  [
    {
      "id": "<uuid>",
      "name": "<string>"
    },
    ...
  ]
  ```
- **Fields:**
  - `id`: Room UUID
  - `name`: Room name
