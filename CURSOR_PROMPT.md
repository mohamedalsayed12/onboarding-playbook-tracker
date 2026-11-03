# Build brief — Onboarding Playbook Tracker

Portfolio project: multi-tenant customer onboarding tracker with reusable playbooks and a rollout dashboard.

## Product

Operators (platform strategists) create **tenants**, invite users, advance stages (`invited → activated → first_use → active`), attach a **playbook**, and see stuck users / rollout summaries. Customer admins see only their tenant.

## Stack (approved)

Python 3.12, FastAPI, Pydantic v2, pydantic-settings, SQLAlchemy 2.0, psycopg 3, Alembic, PostgreSQL 16, Redis 7, PyJWT, argon2-cffi, pytest + TestClient against real Postgres, uv, ruff, mypy `--strict`, Docker Compose, GitHub Actions.

## Non-negotiables

- Tenant-scoped queries via `accessible_tenant_ids`; misses are **404**, never 403
- Invite tokens hashed (SHA-256), single-use, expired; argon2 passwords; short-lived JWTs
- No emails/names/passwords/tokens in logs — IDs only
- Routers = HTTP only; services = business logic
- Fictional company/person data only in seeds and tests

See [README.md](README.md) and [PORTFOLIO.md](PORTFOLIO.md).
