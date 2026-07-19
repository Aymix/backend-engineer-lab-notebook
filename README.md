# The Engineer's Lab Notebooks

Premium **guided-practice workbooks** for backend and DevOps engineering. Not textbooks and not exam
prep — laboratory manuals, built to be worked in: diagrams to redraw, labs to build, incidents to debug,
and ruled space to write your reasoning by hand.

Two volumes, each accompanying a 14-day speedrun roadmap. Each has one chapter per day, an identical
eleven-part rhythm, and one production project that grows across all fourteen days.

| | Volume | Pages | Build-along project |
|---|---|---:|---|
| **I** | [**The Backend Engineer's Lab Notebook**](backend/) — Java & Spring Boot | 248 | **ShopFlow**, an order-management backend |
| **II** | [**The DevOps Engineer's Lab Notebook**](devops/) — Linux → Kubernetes → GitOps | 321 | **CloudBase**, production cloud infrastructure |

> 📕 [Download Volume I (PDF)](backend/Java-SpringBoot-Backend-Engineer-14-Day-Companion-Workbook.pdf) · 📗 [Download Volume II (PDF)](devops/DevOps-Engineer-14-Day-Companion-Workbook.pdf)

The two volumes are designed to meet: CloudBase's capstone deploys a containerised API, and the natural
one to use is the ShopFlow service built in Volume I.

---

## Volume I — Backend Engineering (Java & Spring Boot)

| Day | Topic | ShopFlow milestone |
|----:|-------|--------------------|
| 1 | Spring Boot Internals | Base module: layered packages, typed config, profiles |
| 2 | Database Mastery | Schema, constraints, composite index, migration |
| 3 | JPA & Hibernate | Entity graph, optimistic locking, one-query listing |
| 4 | REST API Design | DTOs, validation, error shape, pagination, OpenAPI |
| 5 | Spring Security | JWT login/refresh, BCrypt, roles, CORS |
| 6 | Testing | Unit + Testcontainers + MockMvc, incl. auth failures |
| 7 | Clean Architecture | Validator, domain event, async listener |
| 8 | Docker | Multi-stage image + Compose (app + Postgres + Redis) |
| 9 | Redis & Caching | Cached reads, evict-on-write, TTL |
| 10 | Messaging | RabbitMQ, retries, dead letter queue |
| 11 | JVM & Concurrency | Bounded thread pool, Actuator, custom metrics |
| 12 | CI/CD | GitHub Actions: test, build, tag by SHA, push |
| 13 | Production Readiness | Circuit breaker, rate limiting, probes, Grafana |
| 14 | Capstone | Assemble, verify and present the backend |

## Volume II — DevOps Engineering

| Day | Topic | CloudBase milestone |
|----:|-------|---------------------|
| 1 | Linux & the Command Line | Base host: bootstrap script, service user, systemd unit |
| 2 | Git & Version Control | Branch protection, CODEOWNERS, secret-blocking hook |
| 3 | Networking for DevOps | /16 VPC design, public/private subnets, bastion, SGs |
| 4 | Docker Deep Dive | Hardened multi-stage image, non-root, namespaces & cgroups |
| 5 | Kubernetes Fundamentals | Deployment, Service, config/secrets, probes |
| 6 | Kubernetes in Production | Helm, Ingress + TLS, HPA, RBAC |
| 7 | Terraform (IaC) | Network in code, remote state with locking |
| 8 | Ansible | Idempotent role replacing the bootstrap script |
| 9 | CI/CD Engineering | test → scan → build → push, promoted not rebuilt |
| 10 | Cloud Infrastructure on AWS | ALB, cluster, RDS private, least-privilege IAM |
| 11 | Monitoring & Observability | Prometheus, Grafana, correlated logs, one real SLO |
| 12 | Security & Secrets | Secrets manager, image-scan gate, NetworkPolicies |
| 13 | GitOps & Deployment | Argo CD, canary gated on SLO, rehearsed rollback |
| 14 | Capstone | Assembly, DR drill, runbook, architecture review |

---

## The eleven parts of every chapter

1. **The Big Picture** — what problem it solves, where it fits, how it links to earlier days
2. **Concept Map** — one page holding the whole territory and its vocabulary
3. **Guided Learning** — what / why it exists / how it works internally / when / when not / production example
4. **Visualizations** — redraw the architecture from memory
5. **Guided Hands-On Lab** — build it step by step; the book guides the decisions, you write the code
6. **Thinking Exercises** — engineering reflections, not quizzes
7. **Debugging Practice** — a real incident: Observe → Hypothesise → Investigate → Root cause → Fix → Prevent
8. **Mini-Labs** — Beginner, Intermediate, Production-style
9. **Engineering Notes** — senior judgment, trade-offs, cost and reliability thinking
10. **Build-Along Project** — extend the one project that runs across all 14 days
11. **Chapter Summary** — takeaways, cheat sheet, CLI reference, official docs, production checklist

Colour-coded margin notes flag different kinds of thinking — *senior insight*, *production tip*,
*security warning*, *design trade-off*, *cloud cost*, *reliability principle*, *behind the scenes* and more —
alongside ~135 hand-drawn TikZ diagrams across the two volumes.

---

## Building from source

Requires TeX Live with `tcolorbox`, `tikz`, `listings`, `fontawesome5`, `FiraSans` and `sourcecodepro`.
No shell-escape needed.

```bash
cd backend   # or: cd devops
pdflatex -jobname=build/main main.tex   # run twice (TOC + cover positioning)
```

### Layout

```
backend/ | devops/
  main.tex              # master document
  preamble.tex          # design system: colours, callouts, code boxes, diagram styles
  frontmatter.tex       # cover, how-to-use, callout legend, the 14-day arc, TOC
  appendix.tex          # interview cheat sheet, build tracker, glossary
  chapters/
    chapter01.tex ...   # one file per day
```

To restyle a whole volume, edit its `preamble.tex` — colours and callout definitions live at the top.
Volume II's preamble extends Volume I's with infrastructure diagram styles (VPC/subnet zones, cloud and
Kubernetes node shapes), Terraform/HCL and terminal-output code boxes, and a cloud-console illustration frame.

## Licence

This repository is **dual-licensed** — © 2026 Aymix. See [LICENSE](LICENSE) for the full breakdown.

| Part | Files | Licence | You may |
|------|-------|---------|---------|
| **The code** — LaTeX design system & build machinery | `*/preamble.tex`, `*/main.tex`, `.gitignore` | [MIT](LICENSE-CODE) | Use, modify and redistribute freely, **including commercially**. Build your own book with it. |
| **The content** — the workbooks themselves | `*/chapters/*.tex`, `*/frontmatter.tex`, `*/appendix.tex`, `README.md`, the PDFs | [CC BY-NC-ND 4.0](LICENSE-CONTENT) | Share with attribution for **non-commercial** use. No selling, no modified redistributions. |

In short: **the design system is yours to build on; the workbooks are free to read and share, but not to
sell or republish altered.** Every source file carries an `SPDX-License-Identifier` comment.

For commercial use, translations, derivative works, or teaching licences, get in touch via
[github.com/Aymix](https://github.com/Aymix).
