![ACME](https://github.com/catherineisonline/dashboard-with-nextjs/blob/main/public/hero-desktop.png?raw=true)

# ACME is a full-stack project designed to help you learn the foundations of Next.js

[Live](https://dashboard-with-nextjs-azure.vercel.app/) | [Course Curriculum](https://nextjs.org/learn)

## About
ACME is a full-stack project I built to learn the foundations of Next.js. The website includes a dashboard where users can monitor invoices, view revenue stats, and check customer details.

## Installation

- Clone the repo: `git clone https://github.com/catherineisonline/dashboard-with-nextjs.git`

- Navigate into the project folder: `cd acme`

- Install dependencies using pnpm: `pnpm install`

- Set up environment variables by creating a `.env` file in the root and adding your variables:

```
AUTH_SECRET=your_auth_secret_here
AUTH_URL=http://localhost:3000/api/auth

DATABASE_URL=your_database_url_here
DATABASE_URL_UNPOOLED=your_unpooled_database_url_here

PGHOST=your_pg_host
PGUSER=your_pg_user
PGPASSWORD=your_pg_password
PGDATABASE=your_pg_database

NEXT_PUBLIC_STACK_PROJECT_ID=your_public_stack_project_id
NEXT_PUBLIC_STACK_PUBLISHABLE_CLIENT_KEY=your_public_client_key
STACK_SECRET_SERVER_KEY=your_secret_server_key
```
- Run the development server with `pnpm run dev`

- Open your browser at `http://localhost:3000`


## Dependencies

- next (latest)
- react (latest)
- react-dom (latest)
- next-auth (5.0.0-beta.25)
- tailwindcss (3.4.17)
- postgres (^3.4.6)
- typescript (5.7.3)


## Things I learned and implemented

1. Created a database through Vercel on Neon (Serverless Postgres). Populated this database with the provided data.
2. Fetched this data on the server using Server Components. This reduces the client-side JS bundle and prevents your database secrets from being exposed to the client. Rule of thumb: if we have any data fetching or secrets, use Server Components.
3. Used SQL to fetch the data, which was already pre-written, but I learned how you can cut down the amount of data if you need something specific instead of requesting the entire data and cutting it down on the client side.
4. Applied Streaming to make sure slow data requests don’t block the entire website. The user can start some type of interaction with the UI. For example, imagine you have a navigation and dashboard with some stats. You show the nav right away and add a loader to the stats table so the user isn’t completely blocked from doing anything.
5. Practiced how to handle search functionality using URL parameters instead of creating states. As a general rule, if you want to read something from a URL (e.g. /products?category=shoes), use the useSearchParams() hook because there is no need to go to the server.

## Contributions

Please note that this project is part of a Next.js learning course and is not fully functional. For this reason, please avoid creating issues or pull requests. Thank you for understanding!