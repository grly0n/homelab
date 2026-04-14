# General Information

- Name: immich
- Type: VM
- Operating system: Debian GNU/Linux 13 (trixie)
- Kernel version: 6.17.13

# Hardware Information

- CPUs: 3
- RAM: 6 GiB
- Storage: 150 GiB

# Network Information

- IP address: `192.168.50.11/24`
- Default gateway: `192.168.50.1`

# Description

[Link to service](https://immich.home.arpa)

Runs Immich, a self-hosted personal photo and video storage solution to replace Google Photos. A Portainer instance is used to manage the four containers that comprise Immich. Immich and Portainer are both updatable by running shell scripts located in the `/home/george` directory. A Portainer Edge Agent connects this Portainer instance to the main server running on the `docker` LXC for remote management.

The Immich server interface runs on TCP port 2283. A mobile application enables manual syncronization between Apple Photos and Immich.
