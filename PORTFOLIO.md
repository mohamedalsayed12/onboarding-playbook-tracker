# Portfolio case study — Onboarding Playbook Tracker

A backend + dashboard for **B2B customer onboarding**: create accounts (tenants), invite users, move them through stages with a reusable playbook, and surface who is stuck.

**Live demo:** [conduct-playbook-api.onrender.com/dashboard](https://conduct-playbook-api.onrender.com/dashboard)  
(Free host cold-starts after idle — first load can take ~30–60s. Click **View demo data** for an instant look.)

**Repo:** https://github.com/mohamedalsayed12/onboarding-playbook-tracker

---

## Problem

After a software sale, a small customer-success / deployment team often has to onboard many end users per account. Without a shared system, invites, stage tracking, and “what good looks like” stay in spreadsheets and people’s heads.

## Solution

Operators can:

1. Create a **tenant** and invite its users  
2. Advance each user through **`invited → activated → first_use → active`**  
3. Apply a reusable **playbook** (ordered steps per stage) to every account  
4. See **who is stuck**, a **rollout summary** per account, and **average time in stage**

Customer admins only see **their** tenant.

## Stack

Python 3.12 · FastAPI · Pydantic v2 · SQLAlchemy 2 · PostgreSQL 16 · Redis 7 · Alembic · argon2 · PyJWT · Docker Compose · ruff · mypy `--strict` · pytest · Render

## Security highlights

- Tenant-scoped queries; inaccessible tenants return **404** (not 403)  
- Invite tokens hashed (SHA-256), expiry + single use  
- argon2 passwords; short-lived JWTs  
- Logs: IDs only — no emails, names, passwords, or tokens
