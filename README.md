# nearpay-infra

> Host provisioning and hardening (Ansible), WireGuard mesh, k3s install, Cloudflare/GitHub/object-storage (Terraform), cluster bootstrap (Argo CD, OpenBao).

| | |
|---|---|
| Group | Platform |
| Kind | IaC |
| Ships as | netcup hosts, Cloudflare, GitHub org, object storage |
| Owns | Hosts, edge, org settings |
| Depends on (published artifacts only) | — |
| Roadmap phase | P0 Foundations |

## Documentation

This repo stays surgical: design docs live in [`nearpay-brain`](../nearpay-brain/README.md), not here.

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

Scaffold only. Implementation starts in phase **P0 Foundations** (`nearpay-brain/roadmap/roadmap.md`).
