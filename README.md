# The Backend Engineer's Lab Notebook

A **248-page guided-practice workbook** for Java & Spring Boot backend engineering — built as a companion
to a 14-day speedrun roadmap. One chapter per day, one production backend built across all fourteen.

This is not an exam book and not a second textbook. It is a **lab manual**: a place to work, build,
debug, and reflect — with write-in space on the page.

> **[📕 Download the PDF](Java-SpringBoot-Backend-Engineer-14-Day-Companion-Workbook.pdf)** · A4 · 248 pages

---

## What it covers

| Day | Topic | ShopFlow milestone you build |
|----:|-------|------------------------------|
| 1 | Spring Boot Internals | Base module: layered packages, typed config, profiles, `/ping` |
| 2 | Database Mastery | Schema + constraints + composite index + migration |
| 3 | JPA & Hibernate | Order/OrderItem/Product entities, locking, one-query listing |
| 4 | REST API Design | Order API with DTOs, validation, errors, pagination, OpenAPI |
| 5 | Spring Security | JWT login/refresh, BCrypt, roles, locked-down CORS |
| 6 | Testing | Unit + Testcontainers + MockMvc coverage, incl. auth failures |
| 7 | Clean Architecture | Refactor: validator, domain event, async email listener |
| 8 | Docker | Multi-stage image + Compose (app + Postgres + Redis) |
| 9 | Redis & Caching | Cached catalog reads, evict-on-write, TTL |
| 10 | Messaging | `OrderPlaced` to RabbitMQ, retries, dead letter queue |
| 11 | JVM & Concurrency | Bounded thread pool, Actuator, custom metrics |
| 12 | CI/CD | GitHub Actions: test, build, tag by SHA, push image |
| 13 | Production Readiness | Circuit breaker, rate limiting, liveness/readiness, Grafana |
| 14 | Capstone | Assemble, verify, and present the whole backend |

Plus three appendices: an **interview cheat sheet**, the **ShopFlow build tracker**, and a **glossary**.

## The eleven parts of every chapter

Every chapter follows the same rhythm, so you always know where you are:

1. **The Big Picture** — why this exists, where it fits, how it connects to earlier days
2. **Concept Map** — one picture of the whole territory and its vocabulary
3. **Guided Learning** — what / why / how-internally / when / when-not / production / mistakes
4. **Visualizations** — redraw the key diagrams from memory
5. **Guided Coding Lab** — build a feature step by step (guided, not copy-paste)
6. **Thinking Exercises** — reflection prompts with ruled write-in space
7. **Debugging Practice** — Observe → Hypothesise → Verify → Fix → Prevent
8. **Mini-Labs** — Beginner, Intermediate, Production-style
9. **Engineering Notes** — how experienced engineers actually reason
10. **Build-Along Project** — extend **ShopFlow**, one backend across all 14 days
11. **Chapter Summary** — takeaways, pitfalls, a one-page cheat sheet, what's next

## The build-along project: ShopFlow

An order-management backend — customers browse products, place orders and track status; admins manage the
catalog. Deliberately a **small domain carrying a large amount of engineering weight**: exactly the shape of
a strong take-home assignment. Depth over breadth.

## Design

Colour-coded margin notes flag different kinds of thinking — *senior mindset*, *production tip*,
*performance*, *security warning*, *database insight*, *interview insight*, *common misconception*, and
*behind the scenes* — alongside ~60 hand-drawn TikZ diagrams (bean lifecycle, request pipeline, JWT flow,
circuit-breaker state machine, cache-aside, DLQ, JVM heap, and more).

---

## Building from source

Requires a TeX Live installation with `tcolorbox`, `tikz`, `listings`, `fontawesome5`, `FiraSans`, and
`sourcecodepro`. No shell-escape needed.

```bash
pdflatex -jobname=build/main main.tex   # run twice (TOC + cover positioning)
```

### Layout

```
main.tex              # master document
preamble.tex          # design system: colours, callouts, code boxes, diagram styles
frontmatter.tex       # cover, how-to-use, callout legend, 14-day arc, TOC
appendix.tex          # interview cheat sheet, build tracker, glossary
chapters/
  chapter01.tex ...   # one file per day
```

To restyle the whole book, edit `preamble.tex` — colours and callout definitions live at the top.

## Licence

This repository is **dual-licensed** — © 2026 Aymix. See [LICENSE](LICENSE) for the full breakdown.

| Part | Files | Licence | You may |
|------|-------|---------|---------|
| **The code** — LaTeX design system & build machinery | `preamble.tex`, `main.tex`, `.gitignore` | [MIT](LICENSE-CODE) | Use, modify and redistribute freely, **including commercially**. Build your own book with it. |
| **The content** — the workbook itself | `chapters/*.tex`, `frontmatter.tex`, `appendix.tex`, `README.md`, the PDF | [CC BY-NC-ND 4.0](LICENSE-CONTENT) | Share with attribution for **non-commercial** use. No selling, no modified redistributions. |

In short: **the design system is yours to build on; the workbook is free to read and share, but not to
sell or republish altered.** Every source file carries an `SPDX-License-Identifier` comment stating which
licence governs it.

For commercial use, translations, derivative works, or teaching licences, get in touch via
[github.com/Aymix](https://github.com/Aymix).
