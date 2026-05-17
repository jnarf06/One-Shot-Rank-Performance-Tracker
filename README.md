# PromptRank Tracker

PromptRank Tracker is a GitHub-ready SaaS dashboard for tracking keyword rankings and AI prompt visibility across SEO and AI search workflows.

## Stack

- Next.js 16 App Router, satisfying the requested Next.js 14+ baseline
- TypeScript
- Tailwind CSS and shadcn/ui-style components
- Prisma ORM with PostgreSQL
- NextAuth credentials authentication
- Recharts analytics
- CSV and PDF exports

## Setup

1. Install dependencies:

```bash
npm install
```

2. Copy environment variables:

```bash
cp .env.example .env
```

3. Update `DATABASE_URL` and `NEXTAUTH_SECRET` in `.env`.

4. Run Prisma migration and seed data:

```bash
npm run db:migrate -- --name init
npm run db:seed
```

5. Start the app:

```bash
npm run dev
```

Demo login after seeding:

- Email: `demo@promptrank.io`
- Password: `demo12345`

## Scripts

- `npm run dev` starts the development server.
- `npm run build` generates Prisma Client and builds Next.js.
- `npm run lint` runs Next.js linting.
- `npm run db:migrate` creates and applies Prisma migrations.
- `npm run db:seed` loads demo projects, keywords, prompt results, and reports.

## Future Integrations

Provider stubs live in `lib/providers.ts` for SERP APIs and AI answer APIs such as OpenAI, Perplexity, Gemini, and Claude. The current product supports manual rank and AI result entry first, so teams can onboard clients before automation is connected.

## File Structure

```text
app/                  App Router pages, layouts, API routes, loading and error states
components/           Reusable dashboard, chart, form, and shadcn/ui-style components
lib/                  Auth, Prisma client, analytics helpers, server actions, export helpers
prisma/               PostgreSQL schema, initial migration, and seed data
types/                NextAuth session typing
public/               Static assets
```
