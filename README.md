# Nuxt Task Manager

A simple task management application built with Nuxt.js, Vue.js, and Drizzle ORM.

## Features

- Create new tasks
- View existing tasks
- User-friendly interface with Pico.css

## Technologies Used

- Nuxt.js 3
- Vue.js 3
- Drizzle ORM (with Turso/libSQL)
- Pico.css
- TypeScript
- ESLint

## Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/username/repository-name.git
    ```
2.  **Install dependencies:**
    ```bash
    pnpm install
    ```
3.  **Set up environment variables:**
    -   Copy `env.example` to `.env`.
    -   Update `.env` with your Turso database URL and auth token.
        ```
        TURSO_DATABASE_URL="your-turso-db-url"
        TURSO_AUTH_TOKEN="your-turso-auth-token" # Optional for local development if local replica is used
        ```
4.  **Apply database migrations:**
    -   Ensure Drizzle Kit is installed (`pnpm install -D drizzle-kit` if not already).
    -   Run `pnpm exec drizzle-kit generate` to create migration files if you made schema changes (see `lib/db/schema.ts`).
    -   Run `pnpm exec drizzle-kit push` to apply migrations. This command typically infers the dialect from `drizzle.config.ts`. For more specific commands or troubleshooting, refer to the Drizzle ORM and Drizzle Kit documentation.
5.  **Run the development server:**
    ```bash
    pnpm run dev
    ```
6.  Open http://localhost:3000 in your browser.

## Available Scripts

-   `pnpm run dev`: Starts the development server.
-   `pnpm run build`: Builds the application for production.
-   `pnpm run generate`: Generates static assets (if applicable).
-   `pnpm run preview`: Previews the production build.
-   `pnpm run lint`: Lints the codebase.
-   `pnpm run lint:fix`: Lints and automatically fixes issues.

## Project Structure

-   `components/`: Vue components.
    -   `app/`: Application-specific components like `nav-bar.vue`.
-   `pages/`: Nuxt page components for routing.
    -   `create.vue`: Page to create tasks.
    -   `index.vue`: Main page to list tasks.
    -   `tasks/[id].vue`: Page to view a specific task.
-   `server/`: Backend server logic.
    -   `api/`: API endpoints.
-   `lib/`: Shared libraries and utilities.
    -   `db/`: Database related files (schema, migrations, Drizzle client).
    -   `env.ts`: Environment variable handling.
-   `public/`: Static assets.
-   `nuxt.config.ts`: Nuxt.js configuration.
-   `drizzle.config.ts`: Drizzle ORM configuration.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing

Contributions are welcome! Please feel free to open an issue or submit a pull request.