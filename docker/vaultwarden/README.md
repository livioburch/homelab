# 🔑 Vaultwarden – Enterprise Password Management

This directory contains the deployment stack for Vaultwarden, a lightweight, self-hosted implementation of the Bitwarden API written in Rust. Following strict security zoning principles, this service runs completely isolated on its own Proxmox VM.

## ⚙️ Security & Architecture Design

* **Strict Isolation:** Deployed on a separate virtual machine to minimize the blast radius in case other application networks are ever compromised.
* **End-to-End Encryption:** All credential synchronization and data storage are fully encrypted before leaving the client application.
* **Hardened Configurations:** Public signups are strictly disabled (`SIGNUPS_ALLOWED=false`) once the administrative account is established.

## 🚀 Deployment

1. Define your secure administrative token using a hash inside a `.env` file or your compose configuration.
2. Launch the vault stack:
   ```bash
   docker compose up -d
