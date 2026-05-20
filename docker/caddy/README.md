# 🔒 Caddy – Central Edge Router & Reverse Proxy

This directory contains the containerized deployment for Caddy, acting as the secure reverse proxy and entry point for all web services within my production environment.

## ⚙️ Features & Architecture

* **Automated TLS:** Caddy automatically provisions, configures, and renews SSL/TLS certificates using Let's Encrypt or ZeroSSL via the ACME protocol.
* **Production Ingress:** It securely routes incoming external traffic (Ports `80` & `443`) to the respective backend containers using internal docker networks or isolated VM paths.
* **Minimal Footprint:** Deployed using the lightweight `caddy:2-alpine` image to ensure high security and minimal resource overhead.

## 📁 File Structure

* `docker-compose.yml` — Defines the container runtime, state volumes, and port bindings.
* `Caddyfile` — Contains the routing logic and reverse proxy definitions.

## 🚀 Deployment

1. Ensure the `Caddyfile` contains your desired routing rules.
2. Spin up the container:
   ```bash
   docker compose up -d
