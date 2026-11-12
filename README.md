# nearpay-infra

Planned infrastructure-as-code for NearPay's server stage: host provisioning and hardening (Ansible), WireGuard mesh, k3s install, Cloudflare, GitHub and object-storage configuration (Terraform), cluster bootstrap (Argo CD, OpenBao). **This repo is a scaffold: it contains the directory layout and no code yet.**

Part of [NearPay](https://github.com/nearpay-money/nearpay) — start there for the live demo, the architecture diagram and the full "do X, see Y" walkthrough.

- **Where it sits:** nothing uses it today. The closed beta that runs on NEAR mainnet (https://nearpay.money) is deployed from [nearpay-deploy](https://github.com/nearpay-money/nearpay-deploy) as one Docker Compose stack; this repo is for Stage 5 (a hardened server) and the later two-site k3s target.
- **Status:** scaffold only. Every directory below holds a `.gitkeep` and nothing else.

| | |
|---|---|
| Group | Platform |
| Kind | IaC |
| Ships as | netcup hosts, Cloudflare, GitHub org, object storage |
| Owns | Hosts, edge, org settings |
| Depends on (published artifacts only) | — |
| First built in | Stage 5 (step 5.1) |

## Documentation

Design docs live in [`nearpay-brain`](https://github.com/nearpay-money/nearpay-brain), not here.

- [`lld/platform.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/lld/platform.md) — low-level design this repo is implemented from
- [`lld/audits/platform.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/lld/audits/platform.md) — audit findings already folded into the LLD
- [`roadmap/development-plan.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/roadmap/development-plan.md) — stage and step this repo is built in
- [`architecture/hld.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/architecture/hld.md) — system design
- [`architecture/repositories.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/architecture/repositories.md) — repo topology and dependency rules
- [`architecture/infrastructure.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/architecture/infrastructure.md)
- [`decisions/ADR-0011-netcup-k3s-two-site.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/decisions/ADR-0011-netcup-k3s-two-site.md)

## Layout

```
nearpay-infra/
├── ansible/
│   ├── inventories/
│   │   ├── production/
│   │   └── staging/
│   └── roles/
│       ├── base-hardening/
│       ├── docker-host/
│       ├── k3s/
│       ├── observability-host/
│       └── wireguard/
├── bootstrap/
│   ├── argocd/
│   └── openbao/
├── terraform/
│   ├── cloudflare/
│   ├── github/
│   └── object-storage/
└── .github/
    └── workflows/
```

## Verify this repo

There is nothing to run. What can be checked by reading:

1. `find . -type f -not -path './.git/*'` → `README.md`, `AGENTS.md`, `LICENSE`, `.gitignore`, `.github/CODEOWNERS` and 13 `.gitkeep` placeholders. No Ansible roles, Terraform modules or workflows exist yet.
2. The design this repo will implement: [`lld/platform.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/lld/platform.md) §2 and [`architecture/infrastructure.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/architecture/infrastructure.md). How the beta is actually hosted: `lld/platform.md` §1.4.

## Status

Scaffold only. Implementation starts in **Stage 5 (step 5.1)** ([`roadmap/development-plan.md`](https://github.com/nearpay-money/nearpay-brain/blob/main/roadmap/development-plan.md)). No infrastructure is managed from here.

## Built with

Nothing yet. Planned tools: Ansible, Terraform, WireGuard, k3s, Argo CD, OpenBao. Licence: Apache-2.0 (`LICENSE`).

Code and documentation are written with AI assistance (Claude) under human direction and review. Built for the NEAR Hackathon (Nov 2026).
