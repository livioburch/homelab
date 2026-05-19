# Pi-hole Deployment (Proxmox LXC)

Instead of running my primary DNS server inside Docker, I decided to deploy Pi-hole inside a dedicated **Proxmox LXC (Linux Container)**. This ensures maximum uptime, low overhead, and a dedicated IP address within my network management VLAN.

## Environment Details
* **Hypervisor:** Proxmox VE
* **Container Type:** LXC (Unprivileged)
* **Base OS:** Debian 11
* **Resources Allocated:** 1 vCPU, 512 MB RAM, 8 GB Storage

## Installation Steps

The container was provisioned and updated, followed by the official network installation script:

```bash
curl -sSL [https://install.pi-hole.net](https://install.pi-hole.net) | bash
