# General Information

- Name: docker
- Type: LXC
- Operating system: Debian GNU/Linux 13 (trixie)
- Kernel version: Linux 6.17.13

# Hardware Information

- CPUs: 6
- RAM: 8 GiB
- Storage: 62.44 GiB

# Network Information

- IP address: `192.168.50.2/24`
- Default gateway: `192.168.50.1`

# Description

Main LXC running services on the homelab through a combination of Docker images and services. Currently running these services:

- [Docker](#docker)
- [Portainer](#portainer)
  - [Grafana](#grafana)
  - [Caddy](#caddy)
  - [Prometheus](#prometheus)
- [Samba](#samba)

# Services

## Docker

- Version: 29.3.0 (Community)

## [Portainer](https://portainer.home.arpa)

- Version: Community Edition 2.40.0 STS
- Deployed using `docker compose`
- YAML file path: `/home/george/docker-compose.yml`
- Active ports:
  - 8000
  - 9443
- Connected to Edge Agent running on Immich VM for remote management
- Running services:
  - [Grafana](#grafana)
  - [Caddy](#caddy)

Docker container manager with an easy-to-use web interface.

## [Grafana](https://grafana.home.arpa)

- Version: OSS latest release
- Deployed through [Portainer](#portainer) web interface
- Active ports:
  - 3000

Dashboard for monitoring various metrics and analytics (to be configured)

## Caddy

- Version: 2.11.2
- Deployed as a Docker container (manage through Portainer)
- Active ports:
  - 80
  - 443
- Manage Caddyfile at `/opt/caddy/`

Reverse proxy for redirecting hostnames to IP address + port combinations over HTTPS with self-signed certificates. Used in conjunction with Pi-hole to provide local DNS records for services running on the homelab. Refer to the Pi-hole documentation for more information.

## Prometheus

- Version 3.11.2
- Deployed as a Docker container
- YAML file path: `/home/george/prometheus/docker-compose.yml`
- Active ports:
  - 9090
  - 9100

Data source for Grafana monitoring dashboards. Includes a node exporter container.

## Samba

- Running as a background service on LXC
- Manage configuration at `/etc/samba/smb.conf`
- Login: user / password
- Mounted volumes:
  - `/mnt/samba_primary`
    - 1.8T external HDD (currently formatted as HFS+, need to move files and reformat)
  - `/mnt/samba_backup`
    - 2.7T external HDD (also formatted as HFS+)
