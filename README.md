# Active Cybersecurity Architecture — OPNsense, pfSense & VPNs

**Author:** Pedro Gonçalves  
**Project type:** Hands-on virtual cybersecurity laboratory  
**Focus:** Network security engineering, segmentation, secure remote access and access control

## Overview

This project documents the design, configuration and validation of a segmented security infrastructure built with **OPNsense**, **pfSense**, **VyOS**, **Windows Server 2022**, **Windows 10**, and **CentOS 7**. It explores practical network-defense controls in a controlled virtual lab, including DNS enforcement, firewall policies, NAT, centralized RADIUS authentication, and multiple VPN technologies.

📄 **[Read the illustrated technical report (PDF)](Active_Cybersecurity_OPNsense_pfSense_VPN_Pedro_Goncalves.pdf)**

## Architecture

| Component | Role |
|---|---|
| VyOS | WAN gateway, routing and source NAT |
| OPNsense | Main firewall; GREEN, ORANGE/DMZ and BLUE guest zones |
| pfSense | Second firewall, remote network and VPN endpoint |
| Windows Server 2022 | Active Directory, DNS, DHCP and NPS/RADIUS |
| CentOS 7 | DMZ web services, HTTPS and FTP |
| Windows 10 | Client-side verification and VPN access |

### Lab networks

| Zone | Subnet |
|---|---|
| OPNsense GREEN | `172.19.130.0/23` |
| OPNsense ORANGE / DMZ | `172.29.130.64/29` |
| OPNsense BLUE / Guest | `10.55.130.0/24` |
| pfSense GREEN | `10.120.130.0/24` |
| Shared WAN | `10.103.130.0/27` |
| WireGuard (OPNsense lab) | `10.250.130.0/24` |
| WireGuard (pfSense lab) | `10.251.130.0/24` |

## Implemented and documented activities

1. **Network segmentation:** firewall interfaces, aliases, DMZ isolation, routing and NAT.
2. **DNS governance:** Windows DNS, forwarders and firewall rules restricting external DNS access.
3. **Access control:** scheduled website restrictions, domain/category filtering and Squid proxy configuration, including lab SSL inspection.
4. **Centralized authentication:** Windows NPS/RADIUS integration and time-restricted VPN access policies.
5. **IPsec site-to-site:** OPNsense-to-pfSense tunnel configuration and protocol-specific rules.
6. **OpenVPN remote access:** client profiles, certificates, RADIUS authentication and firewall policy.
7. **WireGuard:** remote-access tunnels, DNS policy, full-tunnel routing and selective SSH/RDP restrictions.
8. **Guest network:** captive portal, two-hour vouchers, DHCP and bandwidth shaping.
9. **Validation:** screenshots and checks covering connectivity, DNS, remote services, web access and VPN behavior.

## Evidence and results

The PDF contains an extensive step-by-step laboratory record with configuration screenshots, test outputs, troubleshooting notes and a final assessment. This README summarizes the work; the PDF provides the detailed evidence. Some examples in the source document are exploratory configurations rather than independent proof of production-grade security.

## Security and scope

This is an **educational, isolated laboratory**. All IP addresses are private lab addresses. Example passwords, shared secrets and certificate material from the original exercises should **never be reused** in real environments. HTTPS interception and traffic restrictions are appropriate only in environments where authorized and properly disclosed.

## Skills demonstrated

`Network Security` · `OPNsense` · `pfSense` · `VyOS` · `IPsec` · `OpenVPN` · `WireGuard` · `RADIUS` · `Windows Server` · `DNS` · `NAT` · `Firewall Rules` · `Proxy` · `Captive Portal` · `Traffic Shaping` · `Troubleshooting`

---

**Pedro Gonçalves** — Cybersecurity & Network Engineering Portfolio
