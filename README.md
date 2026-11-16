# AdGuard Home – DNS Security Homelab

## Project Overview

This project demonstrates the deployment of AdGuard Home as a DNS-based network filtering solution in a home lab environment.

An old HP Pavilion laptop was repurposed as a dedicated DNS filtering server running Linux Mint 22.3.

The main goal is to monitor DNS traffic, block unwanted domains, and improve visibility and security across the local network.

## Hardware & Software

| Component | Details |
|---|---|
| Device | HP Pavilion 17 |
| CPU | Intel Core i3-3110M |
| RAM | 6 GB |
| Storage | 750 GB HDD |
| Operating System | Linux Mint 22.3 |
| AdGuard Home | v0.107.80 |

## Network Configuration

| Setting | Value |
|---|---|
| Hostname | Matrix-lab |
| Server IP | 192.168.100.131 |
| Network | 192.168.100.0/24 |
| DNS Port | 53 (TCP/UDP) |
| Web Interface | http://192.168.100.131 |
| Upstream DNS | Cloudflare (1.1.1.1) |

## DNS Filtering

The following blocklists were enabled:

- AdGuard DNS Filter
- AdAway Default Blocklist

These lists help block advertisements, trackers, and unwanted domains.

## Firewall Configuration

UFW (Uncomplicated Firewall) was configured to allow only the required services from the local network:

| Port | Protocol | Purpose |
|---|---|---|
| 80 | TCP | Web Interface |
| 53 | UDP | DNS |
| 53 | TCP | DNS |

Access is restricted to the local subnet (192.168.100.0/24).

## Testing & Verification

DNS filtering was tested from a Windows client using:

`nslookup doubleclick.net`

The domain returned `0.0.0.0` and `::`, confirming that the DNS filtering mechanism was working.

The AdGuard Home Query Log also confirmed that the A and AAAA requests were blocked.

## Skills & Knowledge Gained

- Linux system administration
- DNS configuration and troubleshooting
- DNS filtering and blocklist management
- UFW firewall configuration
- Network monitoring and traffic analysis
- DNS query logging and verification

## Project Status

Core deployment, DNS filtering, firewall configuration, and testing have been completed.

Documentation and screenshots are being organized.

## Author

Cybersecurity Homelab Project
