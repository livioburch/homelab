# ⚙️ Livio's Homelab Infrastructure

Welcome to my homelab repository! This project serves as my personal playground and production environment to test, learn, destroy and implement modern IT infrastructure, automation, and networking concepts.

## Architecture Overview

My homelab is built with high availability, security, and automation in mind.

* **Hypervisor:** Proxmox VE
* **Compute Layer (Virtual Machines & LXC):**
  * `LXC-pihole` (Debian): Dedicated lightweight Linux Container for primary DNS.
  * `VM-arr-stack` (Debian): Media Automation & Core I/O Download Clients
  * `VM-vaultwarden` (Debian): Self-hosted, end-to-end encrypted Bitwarden password server
  * `VM-proxy-monitoring` (Debian): Caddy & Centralized Monitoring (Monitoring not online, still in progress)
* **Storage:** Centralized NAS with automated backups
* **Network:** Physical firewall with strict VLAN segmentation (Management, Trusted, IoT, DMZ)

---

## Running Services (Docker)

Most of my services are containerized using Docker and managed via Docker Compose. You can find the configurations in the `docker/` directory:

* **`proxy/` (caddy):** Handles reverse proxying and automated Let's Encrypt SSL certificates.
* **`pihole/`:** Network-wide DNS server and ad-blocking.
More comming SOON!

---

## Scripts & Automation

In the `scripts/` directory, I store my automation scripts written in Bash and Python.

---

## Security Note

> ⚠️ **Important:** To maintain security, all private IP addresses, domain names, API keys, and passwords have been removed from these files and replaced with environment variables (`.env`) or dummy values.

---

## License
This repository is open-source and available under the [MIT License](LICENSE).
