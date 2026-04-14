# General Information

- Name: tailscaled
- Type: LXC
- Operating system: Debian GNU/Linux 13 (trixie)
- Kernel version: 6.17.13

# Hardware Information

- CPUs: 1
- RAM: 512 MiB
- Storage: 7.78 GiB

# Network Information

- IP address: `192.168.50.12/24`
- Default gateway: `192.168.50.1`

# Description

[Link to Tailscale admin page](https://login.tailscale.com/admin/machines)

Runs Tailscale agent for remote access to the Lyonlab network (`192.168.50.0`). Advertises the `192.168.50.0` subnet for hosts connected to the Tailnet to access. The global nameserver is set to the Pi-hole instance (`192.168.50.13`) for local DNS resolution for running services.

The Tailscale agent can be managed via command line with the `tailscale` command.
