# Next.js starter kit: Prisma, PostgreSQL, NextAuth, VineJS, shadcn/ui

A small Next.js (App Router) starter with a typed database layer, validated auth APIs, and a ready UI component setup.

## Stack

- **Next.js** App Router, TypeScript
- **PostgreSQL + Prisma** (`prisma/schema.prisma`, with an initial migration)
- **VineJS** for request validation, with a custom error reporter that returns field-level errors
- **bcrypt** for password hashing
- **NextAuth** (credentials provider)
- **shadcn/ui** + Tailwind CSS (Button, Input, Label)

## What's included

- `POST /api/auth/register`: validates name, username, email, and password (with confirmation), rejects duplicate emails and usernames, hashes the password, and creates the user with Prisma
- `POST /api/auth/login`: credentials login route
- Login and register pages under `src/app/(authpages)/`
- `User` model: id, name, unique username, unique email, hashed password, createdAt

**Status:** the NextAuth credentials provider in `src/app/api/auth/[...nextauth]/options.ts` is still the scaffold and needs to call the login route to be fully wired.

## Getting started

```bash
npm install
echo 'DATABASE_URL="postgresql://user:password@localhost:5432/starter"' > .env
npx prisma migrate dev
npm run dev
```
