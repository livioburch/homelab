# 🎬 Advanced *arr Media Automation Stack

This workspace hosts the orchestration configs for a fully automated media acquisition, curation, and cataloging pipeline. It implements industrial deployment standardizations for container clusters.

## 🧬 Architectural Highlights

* **DRY Code Design:** Utilizes advanced YAML extension anchors (`x-common-keys`) to propagate uniform environments, user IDs (`PUID/PGID: 1000`), local time zones (`Europe/Zurich`), and logging drivers across 7 independent microservices.
* **Unified Storage (Hardlink Efficiency):** All media scrapers and download clients route through a unified `/data` root mount path. This enforces **atomic moves / hardlinking**, bypassing redundant disk copies, saving valuable NVMe/SSD lifespans, and optimizing I/O queues.
* **Resilient Network DNS Routing:** To circumvent bootstrapping race conditions (e.g., after power outages), the stack is configured to route via the local primary DNS `192.168.10.100` (Pi-hole LXC) but retains a robust public fallback node (`1.0.0.1`).

## 🧱 Microservices Orchestrated

* **Radarr / Sonarr / Lidarr:** Automated cataloging engines for Movies, TV Shows, and Music.
* **Bazarr:** Closed-caption and subtitle automation agent.
* **Prowlarr:** Central indexer wrapper and metadata aggregator.
* **qBittorrent:** High-performance, isolated download client with granular torrenting ports.
* **Jellyfin:** Privacy-focused media streaming platform configured with structural Read-Only (`ro`) safety flags over the media library.

## 🚀 Execution

Initialize the entire media infrastructure pipeline on its dedicated bridge network:
```bash
docker compose up -d
