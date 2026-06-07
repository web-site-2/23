# LocalReach AI

A production-ready SaaS platform for lead generation, business discovery, CRM, AI outreach, proposal generation, and sales automation.

Built for agencies, freelancers, web developers, marketing agencies, and business consultants.

## Tech Stack

- **Next.js 15** (App Router)
- **TypeScript**
- **Tailwind CSS** + **Shadcn UI**
- **PostgreSQL** + **Prisma ORM**
- **NextAuth** Authentication
- **OpenAI API** for AI features
- **Google Maps API** for business discovery
- **Resend / SMTP / SendGrid** for email
- **Stripe** for subscriptions
- **Server Actions** for data mutations

## Features

- **Business Discovery** — Search businesses by location and category with table, card, and map views
- **Lead CRM** — Pipeline stages, notes, tags, activity timeline, team assignment
- **AI Website Audits** — Automatic website analysis with scoring and sales opportunities
- **Lead Scoring** — 0-100 score with high/medium/low opportunity levels
- **AI Personalization** — Unique outreach messages per business
- **Bulk Campaigns** — Multi-provider email with open/click tracking and follow-ups
- **Follow-Up Automation** — Day 3, 7, 14 sequences with auto-stop on reply
- **Website Demo Generator** — AI mockups for prospects (Agency plan)
- **Proposal Generator** — AI-powered proposals with PDF export
- **Analytics Dashboard** — Conversion rates, campaign performance, revenue forecasting
- **Team Management** — Role-based access control
- **Subscriptions** — Free, Pro, and Agency plans via Stripe

## Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL database
- API keys (see `.env.example`)

### Installation

```bash
# Clone and install
cd localreach-ai
npm install

# Configure environment
cp .env.example .env
# Edit .env with your credentials

# Set up database
npx prisma db push

# Start development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

### Environment Variables

See `.env.example` for all required variables:

| Variable | Description |
|----------|-------------|
| `DATABASE_URL` | PostgreSQL connection string |
| `NEXTAUTH_SECRET` | Random secret for auth |
| `OPENAI_API_KEY` | OpenAI API key |
| `GOOGLE_MAPS_API_KEY` | Google Places API key |
| `RESEND_API_KEY` | Resend email API key |
| `STRIPE_SECRET_KEY` | Stripe secret key |
| `STRIPE_PRO_PRICE_ID` | Stripe price ID for Pro plan |
| `STRIPE_AGENCY_PRICE_ID` | Stripe price ID for Agency plan |

## Deployment

### Vercel (Recommended)

1. Push to GitHub
2. Import project in Vercel
3. Add environment variables
4. Deploy

The `vercel.json` includes a cron job for follow-up emails every 6 hours. Set `CRON_SECRET` in production.

### Database

Use a managed PostgreSQL provider (Neon, Supabase, Railway):

```bash
npx prisma db push
```

## Project Structure

```
src/
├── app/                    # Next.js App Router pages
│   ├── (auth)/             # Login, register
│   ├── (dashboard)/        # Protected dashboard pages
│   └── api/                # API routes (auth, tracking, webhooks)
├── actions/                # Server Actions
├── components/             # React components
│   ├── ui/                 # Shadcn UI primitives
│   ├── layout/             # Sidebar, header
│   └── [feature]/          # Feature-specific components
├── lib/                    # Utilities and integrations
└── types/                  # TypeScript types
prisma/
└── schema.prisma           # Database schema
```

## Subscription Plans

| Plan | Leads/Month | Price |
|------|-------------|-------|
| Free | 100 | $0 |
| Pro | 5,000 | $49/mo |
| Agency | Unlimited | $149/mo |

## License

MIT
