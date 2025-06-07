![ACME](https://github.com/catherineisonline/dashboard-with-nextjs/blob/main/public/hero-desktop.png?raw=true)

# ACME is a full-stack project designed to help you learn the foundations of Next.js

[Live](https://dashboard-with-nextjs-azure.vercel.app/) | [Course Curriculum](https://nextjs.org/learn)

## About
ACME is a full-stack project I built to learn the foundations of Next.js. The website includes a dashboard where users can monitor invoices, view revenue stats, and check customer details.

## Credentials
* Email: user@nextmail.com
* Password: 123456

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
- zod (^3.25.17)
- bcrypt (^5.1.1)

## Things I learned and implemented

1. Created a database through Vercel on Neon (Serverless Postgres). Populated this database with the provided data.
2. Fetched this data on the server using Server Components. This reduces the client-side JS bundle and prevents your database secrets from being exposed to the client. Rule of thumb: if we have any data fetching or secrets, use Server Components.
3. Used SQL to fetch the data, which was already pre-written, but I learned how you can cut down the amount of data if you need something specific instead of requesting the entire data and cutting it down on the client side.
4. Applied Streaming to make sure slow data requests don’t block the entire website. The user can start some type of interaction with the UI. For example, imagine you have a navigation and dashboard with some stats. You show the nav right away and add a loader to the stats table so the user isn’t completely blocked from doing anything.
5. Practiced how to handle search functionality using URL parameters instead of creating states. As a general rule, if you want to read something from a URL (e.g. /products?category=shoes), use the useSearchParams() hook because there is no need to go to the server.
6. Used server actions for the invoice creation form. To mark a function as a server action, need to make sure we add 'use server' at the start of the module where we write actions, or include it in the action itself if it’s directly created in the Client or Server component.
7. Added Zod TypeScript validation library to validate form data types.
8. Added path revalidation to make sure that the server sends new data for invoices, updates the cache, and reflects new data asap. This works great along with the built-in redirect function to go back to the invoices table.
9. To handle any errors for route segments and show more user-friendly errors, added a built-in error API that allows you to display a fallback UI
10. Implemented form validation for invoice creation and editing using server-side validation using the useActionState hook. A bit confusing at the start, but I think it should be relatively easy after several such implementations.
11. Learned to differentiate between authentication (proving your identity when logging in) and authorization (what you are allowed to see and do).
12. Added authentication using NextAuth.js, authorization to make sure that if a person isn’t logged in, they can’t access the dashboard. Used bcrypt for hashing the password. All this is new for me in practice. I would say it’s a lot in one go, but I think I want to try this again.
13. Added metadata, this was easy.

## Contributions

Please note that this project is part of a Next.js learning course and is not fully functional. For this reason, please avoid creating issues or pull requests. Thank you for understanding!