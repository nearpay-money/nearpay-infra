# nearpay-infra

> Host provisioning and hardening (Ansible), WireGuard mesh, k3s install, Cloudflare/GitHub/object-storage (Terraform), cluster bootstrap (Argo CD, OpenBao).

| | |
|---|---|
| Group | Platform |
| Kind | IaC |
| Ships as | netcup hosts, Cloudflare, GitHub org, object storage |
| Owns | Hosts, edge, org settings |
| Depends on (published artifacts only) | — |
| First built in | Stage 5 (step 5.1) |

## Documentation

This repo stays surgical: design docs live in [`nearpay-brain`](../nearpay-brain/README.md), not here.

- `nearpay-brain/lld/platform.md` — **low-level design (dev-ready; implement from this)**
- `nearpay-brain/lld/audits/platform.md` — audit findings already folded into the LLD
- `nearpay-brain/roadmap/development-plan.md` — stage and step this repo is built in
- `nearpay-brain/architecture/hld.md` — system design
- `nearpay-brain/architecture/repositories.md` — repo topology and dependency rules
- `nearpay-brain/architecture/infrastructure.md`
- `nearpay-brain/decisions/ADR-0011-netcup-k3s-two-site.md`

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

## Status

Scaffold only. Implementation starts in **Stage 5 (step 5.1)** (`nearpay-brain/roadmap/development-plan.md`).

## Built with

Libraries are listed here as they are added (hackathon rule Q-005). Code and documentation are written with AI assistance (Claude) under human direction and review.
