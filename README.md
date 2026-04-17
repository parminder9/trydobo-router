# trydobo-router

Root domain router for `www.trydobo.com`. Uses Vercel rewrites to proxy:

- `/portfolio/*` → portfolio (Vite) deployment
- `/tailor/*`    → job-application-agent (Next.js) deployment

## Setup

1. Deploy portfolio and job-application-agent to Vercel as their own projects. Note their production URLs (e.g. `portfolio-abc.vercel.app`).
2. Edit `vercel.json` and replace `REPLACE_WITH_PORTFOLIO_DEPLOYMENT` and `REPLACE_WITH_TAILOR_DEPLOYMENT` with the real hostnames.
3. Deploy this project to Vercel.
4. Attach `www.trydobo.com` (and `trydobo.com`) to this project in Vercel → Settings → Domains.
5. In GoDaddy, point DNS to Vercel:
   - `A` record for `@` → `76.76.21.21`
   - `CNAME` for `www` → `cname.vercel-dns.com`
