# General Information

- Name: pihole
- Type: LXC
- Operating system: Debian GNU/Linux 13 (trixie)
- Kernel version: Linux 6.17.13

# Hardware Information

- CPUs: 1
- RAM: 512 MiB
- Storage: 3.86 GiB

# Network Information

- IP address: `192.168.50.13/24`
- Default gateway: `192.168.50.1`

# Description

[Link to service](https://pihole.home.arpa/admin)

LXC running Pi-hole as a DNS sink and lookup for local records. TCP port 53 is port forwarded over the network router at 192.168.50.1 / 192.168.12.2 for access on the Lyon Den Wi-Fi network. Devices must use a manual DNS server override and disable IPv6 to select the Pi-hole instance as the only DNS server.

Because of the segmentation of Pi-hole behind a router, Pi-hole is configured to permit all origins for DNS requests and filtering.

Uses the Quad9 (filtered, ECS, DNSSEC) option for the Upstream IPv4 DNS Server. IPv6 forwarding is not enabled.

This LXC is set as the default DNS server for the Lyonlab network automatically advertised through DHCP. This is not used very much as of now because all of the hosts on the network use static addressing for now.
