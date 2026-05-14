# millyweb

Master manifest for all MW Development infrastructure components.

> **Clone everything at once:**
> ```bash
> git clone --recurse-submodules https://github.com/rdmilly/millyweb
> ```

## Component Map

| Component | Repo | Server | Status | Notes |
|-----------|------|--------|--------|-------|
| **helix** | [rdmilly/helix](https://github.com/rdmilly/helix) | VPS1 | ✅ live | Core AI platform — helix-mcp, The Forge, MemBrain, transcript-bridge |
| **mw-lead-pipeline** | [rdmilly/mw-lead-pipeline](https://github.com/rdmilly/mw-lead-pipeline) | Contabo | ✅ live + git-sync | 10k leads, auto-commits on every batch |
| **atrium** | rdmilly/atrium (needs repo) | VPS2 | 🔄 next | Engineering command center, Phase 2 complete |
| **mcp-provisioner** | [rdmilly/mcp-provisioner](https://github.com/rdmilly/mcp-provisioner) | VPS2 | ✅ live | 45 servers, 697 tools |
| **mcp-servers** | [rdmilly/mcp-servers](https://github.com/rdmilly/mcp-servers) | VPS2 | ✅ live | All MCP integration servers monorepo |
| **git-agent** | [rdmilly/git-agent](https://github.com/rdmilly/git-agent) | VPS1 | ✅ live | AI commit pipeline, ghcr.io image |
| **hostinger-watchdog** | [rdmilly/hostinger-watchdog](https://github.com/rdmilly/hostinger-watchdog) | VPS1+VPS2 | ✅ live | VPS health safety daemon |
| **content-pipeline** | [rdmilly/content-pipeline](https://github.com/rdmilly/content-pipeline) | VPS1+Clair | 🔄 v4 in progress | Video capture pipeline |
| **adventures-of-shanghai** | [rdmilly/adventures-of-shanghai](https://github.com/rdmilly/adventures-of-shanghai) | VPS2 | ✅ live | Investigative content brand |
| **paving-agent** | [rdmilly/paving-agent](https://github.com/rdmilly/paving-agent) | TBD | ⏸ deferred | Declarative control plane, PRD written |
| **mw-voice** | [rdmilly/mw-voice](https://github.com/rdmilly/mw-voice) | TBD | 📋 future | AI voice agent for contractors |
| **mw-sites** | [rdmilly/mw-sites](https://github.com/rdmilly/mw-sites) | VPS1+VPS2 | ✅ live | All static sites |

## Infrastructure

| Node | IP | Role |
|------|----|------|
| VPS1 | 72.60.31.69 | Helix + production services |
| VPS2 | 72.60.225.81 | Atrium + MCP layer + dev projects |
| Contabo | 173.212.236.74 | Lead pipeline scraper |
| Clair | 10.0.0.4 | Windows desktop, local capture |

## Submodules

Repos with active submodule links:

```bash
git submodule add https://github.com/rdmilly/helix components/helix
git submodule add https://github.com/rdmilly/mw-lead-pipeline components/mw-lead-pipeline
git submodule add https://github.com/rdmilly/mcp-provisioner components/mcp-provisioner
git submodule add https://github.com/rdmilly/git-agent components/git-agent
git submodule add https://github.com/rdmilly/content-pipeline components/content-pipeline
git submodule add https://github.com/rdmilly/paving-agent components/paving-agent
git submodule add https://github.com/rdmilly/mcp-servers components/mcp-servers
git submodule add https://github.com/rdmilly/hostinger-watchdog components/hostinger-watchdog
git submodule add https://github.com/rdmilly/adventures-of-shanghai components/adventures-of-shanghai
git submodule add https://github.com/rdmilly/mw-sites components/mw-sites
```

## Quick-restore any component

```bash
# Full infrastructure restore from scratch:
git clone --recurse-submodules https://github.com/rdmilly/millyweb
cd millyweb/components/<name>
cp .env.example .env  # fill secrets from Infisical
docker compose up -d
```

## Registry

The live component registry is at **[atrium.millyweb.com](https://atrium.millyweb.com)** under the MW Component Registry project.

The PRD for this component system is at `docs/component-registry-prd.md`.
