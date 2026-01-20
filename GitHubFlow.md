GITHUBFLOW — Explicit Repo Skeleton + Branch/PR Rules (Copastable)

Repo name (example):
- hubebrights-platform

Default branch:
- main (always deployable)

Branch types:
- feature/<short-scope>
- fix/<bug>
- chore/<maintenance>
- docs/<docs>
- spike/<timeboxed-experiment>

Pull Requests:
- Every change to main via PR (no direct pushes)
- PR must include:
  - Summary
  - Screenshots/GIF if UI
  - “Canon impact” note: does this affect Articles/Fiddly Bits/Footnotes?
  - Test notes

Merging:
- Squash merge for feature branches (keeps history clean)
- Rebase locally as needed, but do not rewrite main

Release tags:
- v0.1.0, v0.1.1, etc. (SemVer)
- Tag only from main

Commit convention (simple):
- feat: ...
- fix: ...
- docs: ...
- chore: ...
- refactor: ...
- test: ...

Repo structure (suggested)
/
  README.md
  LICENSE
  .gitignore
  .editorconfig
  .github/
    PULL_REQUEST_TEMPLATE.md
    workflows/
      ci.yml
  apps/
    web/                # React/Vite
    api/                # Express or API routes
  packages/
    canon/              # Canon parsing, manifests, PSD engine
    ui/                 # Shared UI components
    types/              # Shared TypeScript types
  canon/
    manifests/
      canon.index.json
    articles/
      article.01.md
      article.02.md
    fiddly_bits/
      footnotes.md
      identity.md
    citations/
      citations.json
  prisma/
    schema.prisma
    migrations/
  docs/
    architecture.md
    canon_model.md
    psd_spec.md
    threat_model.md

CI (minimum):
- lint + typecheck
- unit tests (even a small set)
- build web

Branch protection (main):
- Require PR
- Require CI pass
- Require 1 review (self-review allowed early; tighten later)

Issue labels:
- canon, psd, identity, footnotes, citations, roles, capabilities, ui, backend, security

Definition of Done:
- Code + tests or notes why not
- Canon links updated if needed
- No new “identity-as-morality” language added
