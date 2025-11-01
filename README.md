# 🏠 Homelab Documentation

This is my **Homelab Documentation**, a complete record of my self-hosted environment — from hardware and architecture to Docker setups, scripts, and operational notes.

This repo serves three main purposes:
1. **Knowledge Base** — so I never need to “guess how I set this up”.
2. **Infrastructure Journal** — to track upgrades, changes, and experiments.
3. **Reference Repository** — for configuration files, commands, and automation scripts.

Note: _You will not find the real homelab here, only some useful scripts_

---

## 🧰 Hardware Overview

This Homelab is running on a consumer-grade hardware, from my old desktop:

* Asus TUF H310M-Plus Gaming/BR, Intel LGA 1151, mATX
  * Only 2 RAM slots → max 32 GB
* Intel Core i5-8400 Coffee Lake 2.80 GHz (2017)
  * 6 Cores
  * UHD Graphics 630
  * VT-x & VT-d
* 16 GB RAM → future 32 GB
  * Kingston HyperX FURY DDR4 8GB 2400 MHz DIMM
  * Kingston HyperX FURY DDR4 8GB 2400 MHz DIMM  
* 500GB M.2 NVMe (1 slot)
  * Kingston A2000 PCIe NVMe - SA2000M8/500G
  * Hosts main OS (Debian + Proxmox VE)
* 120GB SSD (1 SATA port)
  * Kingston A400 120GB SATA - SA400S37/120G
  * Temporary Storage
* 8TB HDD array (1 SATA port)
  * TBD
  * Main Storage
* 1 PCIe x16
  * ASUS GeForce GT 1030 2GB DDR5
  * To Be Upgraded
* 2 PCIe x1 slots
  *  TBD

## 🧰 Services Overview

The system is build with **Proxmox VE**, running on top of Debian.

It hosts several **VMs** and **LXCs**, each dedicated to a domain of the ecosystem:

| VM / LXC | Role | Main Services |
|-----------|------|----------------|
| **vms-media** | Multimedia server | Jellyfin, Navidrome, FileBrowser, Immich |
| **vms-db** | Data services | PostgreSQL, MariaDB, Redis |
| **vmd-dev** | Development sandbox | .NET / Angular apps, APIs |
| **lxc-blog** | Static site host | Jekyll / Hugo for LAN sites |
| **lxc-pihole** | Infrastructure tools | Pi-hole, monitoring, DNS |
| **lxc-proxy** | Infrastructure tools | Caddy (reverse proxy) |
| **backups (external USB)** | Offline safety layer | Manual/automated sync jobs |

---

## 📚 Documentation Structure

All content lives under the [`/docs`](./docs) folder and is grouped by theme.

```
docs/
├── architecture/
│   ├── overview.md
│   ├── network.md
│   ├── storage.md
│   └── backup-strategy.md
│
├── services/
│   ├── media-server.md
│   ├── reverse-proxy.md
│   ├── dns-dhcp.md
│   ├── databases.md
│   └── monitoring.md
│
├── automation/
│   ├── scripts.md
│   ├── dockerfiles.md
│   ├── configs.md
│   └── tasks.md
│
├── notes/
│   ├── troubleshooting.md
│   ├── commands.md
│   ├── updates-log.md
│   └── to-do.md
│
└── assets/
├── diagrams/
└── screenshots/
```
---

## ⚙️ Using MkDocs

### Install MkDocs & Material Theme
```bash
pip install mkdocs mkdocs-material
````

### Run Locally

```bash
mkdocs serve
```

Your site will be available at [http://localhost:8000](http://localhost:8000)

### Deploy to GitHub Pages

```bash
mkdocs gh-deploy
```

---

## 💾 Versioning & Conventions

* Every change or upgrade in the Homelab should be reflected here.
* Config files (e.g. `docker-compose.yml`, `.env`, Caddyfile) go under `/docs/automation/configs/`.
* Shell commands and shortcuts go in `/docs/notes/commands.md`.
* Each file starts with a short description and date.
* Sensitive data (tokens, IPs, etc.) should **never** be committed.

---

## 🚀 Roadmap

* [ ] Add network diagram (Mermaid or draw.io)
* [ ] Document reverse proxy (Caddy) setup
* [ ] Add backup automation script
* [ ] Add energy consumption log
* [ ] Publish as GitHub Pages site

---

*Maintained by [Ruan Carvalho](https://ruancarvalho.com)*
*Last updated: {{ today’s date }}*
