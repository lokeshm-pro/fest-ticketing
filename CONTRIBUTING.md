# Contributing Guide

## Branching strategy (Gitflow-lite)
- `main` – stable, always deployable. Merging here triggers deploy.
- `dev` – integration branch. All features merge here first.
- `feature/<short-name>` – one branch per task, created from `dev`.
- `release/<version>` – optional, cut from `dev` before merging to `main`.

## Workflow
1. Pick or create a GitHub Issue and assign yourself.
2. Fork the repo (or branch from `dev`), then `git checkout -b feature/<short-name>`.
3. Commit small, with clear messages: `feat: add QR ticket endpoint`, `fix: handle sold-out events`.
4. Push and open a Pull Request into `dev`. Link the issue (`Closes #12`).
5. CI must be green and **one teammate must review** before merging.
6. Never push directly to `main` or `dev`.

## Code review checklist
- [ ] Code runs and CI is green
- [ ] Tests added or updated for new behaviour
- [ ] No secrets, passwords or API keys committed
- [ ] Follows project style (flake8 clean)
- [ ] Docs / README updated if needed
- [ ] PR is small and focused on one change

## Team roles
| Member | Role | Owns |
|---|---|---|
| Member 1 | Lead / DevOps | CI/CD pipeline, Terraform, repo setup |
| Member 2 | Backend | `booking-service`, database, tests |
| Member 3 | Docker / Payments | `payment-service`, Dockerfiles, compose, registry |
| Member 4 | Frontend | `frontend`, admin dashboard |
| Member 5 | UX | Research, personas, Figma prototype, usability tests |
