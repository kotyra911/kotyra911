## Matvey Klimanskiy

I used to write backends by hand. Now I specify them, run coding agents in
parallel, and own the part that decides whether their output ships.

"Can a model write this function" stopped being the interesting question a while
ago. The one that matters is **how you accept code you did not write** — and that
is a verification problem, not a prompting one. Most of my work is building that
contour.

### How I work

**A fleet, not a chat window.** Every ticket gets its own git worktree and its own
agent with a scoped `CLAUDE.md`. A dozen or more run at once. Isolation means a bad
run gets thrown away instead of untangled.

**The author never audits itself.** Security review runs as a separate session that
is forbidden from having written the code. It produces numbered findings and never
patches — a model defending its own output is not a reviewer.

**Rules that execute, not rules that persuade.** Constraints live in a custom guard
linter and pre-commit hooks, mirrored exactly in CI on a clean clone so they cannot
be skipped locally. A rule that exists only in prose is a suggestion.

**CI treated as hostile ground.** Actions pinned by commit SHA rather than tags,
read-only default token permissions, no credentials persisted into the work tree.
Build steps run third-party code next to your token, and tag-moving supply-chain
attacks are not hypothetical.

### Selected work

| Project | What it is | Stack |
| --- | --- | --- |
| **WipeSquad** | Teammate matching and clan CRM for Rust — designed, specified and shipped agent-first using the contour above | TypeScript · PostgreSQL · Redis |
| **[shortener-service](https://github.com/klimanskiy1/shortener-service)** | URL shortener with a Docker setup and an isolated test environment | FastAPI · PostgreSQL · Docker · Pytest |
| **[ReqPy CLI](https://github.com/klimanskiy1/htpy-cli-app)** | Terminal HTTP client — a lighter Postman for people who live in the shell | Python · Click · Requests |
| **[WardenV2](https://github.com/klimanskiy1/WardenV2)** | Watches Avito listings and pushes new ones to Telegram; Redis-backed dedup with a 2-day TTL | asyncio · Redis · aiogram |

### Background

Backend engineering is the base the oversight rests on — you cannot review what you
do not understand.

**Languages** — Python, Go
**Web** — FastAPI, Django, Gin, aiogram
**Data** — PostgreSQL, Redis, MySQL, SQLAlchemy
**Infra** — Docker, Linux, Git, GitHub Actions, RabbitMQ

### Elsewhere

[Telegram](https://t.me/matew_1) · [Email](mailto:klimanskiymatvey@gmail.com) · [LinkedIn](https://www.linkedin.com/in/klimanskiy-m)
