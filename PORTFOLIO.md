# Onboarding Playbook Tracker

Multi-tenant B2B onboarding API and dashboard: tenants, invites, stage progression, reusable playbooks, stuck-user views.

**Demo:** https://conduct-playbook-api.onrender.com/dashboard (cold start ~30–60s; use **View demo data**)  
**Repo:** https://github.com/mohamedalsayed12/onboarding-playbook-tracker

## What it demonstrates

- FastAPI services over PostgreSQL 16 with Redis summary caching (invalidate after commit)
- Tenant isolation (inaccessible tenants → 404), argon2 passwords, hashed invite tokens, short-lived JWTs
- SQL rollout aggregates, idempotent seed data, Docker Compose + Render Blueprint

Full setup and API notes: [README.md](README.md).
