# Handcrafted Systems

Are you looking for a privacy-focused, self-hosted, smart home system?

---

## 🚀 Table of Contents
- ✨ [Features](#-features)
- 🔍 [Overview](#-overview)
- ⚠️ [Prerequisites](#️-prerequisites)
- 🛠️ [Installation](#️-installation)
- ❓ [FAQ](#-faq)
- 🙏 [Acknowledgements](#-acknowledgements)
- 🏗️ [Built With](#️-built-with)
- 💬 [Contact](#-contact)

---

## ✨ Features

- 🏠 **Smart home partner** | Guided approach to smart spaces
- 🛡️ **Private, local-first** | Personal, secure access always
- 🙌 **Personalised & custom** | Consultations available
- 🔒 **Pinned versions** | No upstream supply chain risk
- 🚀 **Verified updates** | Latest versions always inspected
- 🧩 **Easy to extend & scale** | Integrated structure
- 🤝 **Direct & community support** | Email/chat & app communities

---

## 🔍 Overview

### 💻 Hardware Layer
| Name                | Purpose                       | Type      | Config             | GUI/CLI | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Raspberry Pi 5 (A)  | Mid-spec, accessible hub      | SBC       | Raspi OS Lite      | Both    | Eth/WiFi+USB  |
| Mini PC (B)         | High-spec, costly hub         | Mini PC   | Proxmox            | Both    | Eth/WiFi+USB  |
| Old PC (C)          | Mid/low-spec, but free        | PC        | Proxmox            | Both    | Eth/WiFi+USB  |
| Zigbee Coordinator  | Sensor & trigger connectivity | Dongle    | Pass-through       | N/A     | /dev/ttyACM0  |
| Raspberry Pi 0 2W   | Core services fallback hub    | SBC       | dietpi             | CLI     | WiFi          |
| HDD/NVMe/SSD        | Shared storage with redunancy | DAS       | mount/fstab/samba  | Both    | USB/Eth       |

### 🛜 Network Layer
| Name                | Purpose                       | Type      | Config             | GUI/CLI | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Zigbee2MQTT         | MQTT translation + Admin      | Container | handcraftedsys     | GUI     | 8290          |
| MQTT                | Pub/Sub                       | Container | handcraftedsys     | N/A     | 1883,9001     |
| Pi-hole             | Local DNS + Ad-blocking       | Container | handcraftedsys     | GUI     | 8081          |

### 🔒 Security Layer
| Name                | Purpose                       | Type      | Config             | GUI/CLI | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| acme.sh             | Local HTTPS                   | Cron      | ~/.acme.sh /certs  | CLI     | N/A           |
| Headscale           | Tailscale control server      | Container | handcraftedsys     | CLI*    | 27896,9090    |
| Tailscale           | Pi-hole Tailnet inclusion     | Service   | cmdline            | CLI     | N/A           |

<sup>* GUI to be added (Headplane / Headscale-UI)</sup>

### 🧩 Application Layer
#### 🌐 Server
| Name                | Purpose                       | Type      | Config             | GUI/CLI | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Caddy               | Reverse-proxy                 | Service   | /etc/caddy *.caddy | GUI     | 80,443        |
| Runtipi             | App store                     | Container | ~/runtipi          | Both    | 9079,9443     |
| DuckDNS             | Dynamic DNS                   | Container | handcraftedsys     | N/A     | N/A           |

#### 📃 Content
| Name                | Purpose                       | Type      | Config             | GUI/CLI | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Apprise             | Notifications                 | Container | handcraftedsys     | Both    | 8000          |
| Uptime Kuma         | Service monitoring & alerts   | Container | handcraftedsys     | GUI     | 8125          |
| TriliumNext         | Notes, diagrams & more        | Container | handcraftedsys     | GUI     | 8267          |

#### 🪄 Automation
| Name                | Purpose                       | Type      | Config             | GUI/CLI | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| openHAB             | Rules, scenes, history        | Service   | /etc/openhab       | Both*   | 8080          |
| ESPHome             | ESP32-based sensors/triggers  | TBD       | TBD                | TBD     | TBD           |
| Home Assistant      | Rules, scenes, history        | TBD       | TBD                | TBD     | TBD           |

<sup>*Karaf console only accessible via CLI</sup>

### 👷‍♂️ Upcoming
| Name                | Purpose                       | Type      | Config             | GUI/CLI | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| raspiBackup         | Scheduled back-ups            | Cron      | TBD                | CLI     | TBD           |
| Authentik/Pocket-ID | OIDC provider                 | Container | handcraftedsys     | GUI     | 8387          |
| Keepalived          | High-availability             | Service   | TBD                | CLI     | TBD           |
| HomeBox             | Organising & tracking         | Container | handcraftedsys     | GUI     | TBD           |
| Syncthing           | P2P file syncing              | Container | handcraftedsys     | GUI     | TBD           |


---

## ⚠️ Prerequisites

### Hardware
Coming soon!

### Runtipi
This repository includes a collection of third-party container applications ("apps") designed exclusively for use with [Runtipi.io](https://runtipi.io/).

> **What is Runtipi?**
>
> Runtipi is an open-source platform that lets you easily self-host and manage web applications on your own server, with a beautiful web UI and one-click app installation.

> [!WARNING]
> These apps are only compatible with Runtipi. You must have a working Runtipi instance to use this App Store. They will not work as standalone Docker containers.

- To get started with Runtipi, see the [official documentation](https://runtipi.io/docs/installation/) or visit the [main GitHub project](https://github.com/meienberger/runtipi).

---

## 🛠️ Installation

### Services
Coming soon!

### Apps (Containers)
1. In the Runtipi dashboard, open `Settings` and go to the `App Stores` tab.
2. Click `Add App Store`, fill in the form with `handcraftedsys` and the URL `https://github.com/handcrafted-systems/runtipi-appstore` then click `Submit`
3. You can now go to the `App Store` page and select the one you just created from the dropdown.

### Cron
Coming soon!

---

## ❓ FAQ

**Q: How do I get started?**  
A: Clear the [prerequisites](#️-prerequisites) then follow the [installation](#️-installation) instructions.

**Q: How is my data handled?**
A: All data is fully controlled & secured by you through the steps noted above. Third-party access is restricted by default & remote support is only available if you choose to add it.

**Q: How will this help me?**
A: Whether you're looking for comfort at home, convenience on the go or the ability to have full control of your choices, data and privacy, this is a great way to avchieve it.

**Q: How can I request a new tool/service/app?**  
A: Reach out to us directly via email/chat or open an issue titled appropriately ex. "[APP] App Name". All requests are vetted for alignment with our clear & friendly approach to smart spaces.

**Q: How are apps updated?**  
A: Via Renovate, with secure CI/CD upcoming.

**Q: Where can I find more about Runtipi?**  
A: See the [official website & documentation](https://runtipi.io/) and the [Runtipi GitHub repository](https://github.com/meienberger/runtipi).

---

## 🙏 Acknowledgements

- Special thanks to all upstream projects and container authors referenced in each app's description.
- Thanks to all (active/passive) contributors and users!

---

## 🏗️ Built With

- Ansible
- Runtipi | openHAB
- Docker & GitHub Containers
- GitHub Actions | Renovate 
- VS Code | Copilot | Gemini
- Tmux | zsh | oh-my-posh
- YAML | JSON | Markdown

---

## 💬 Contact

- 📧 Reach out to us via email: hello at handcrafted dot systems

---

With ❤️😅☕ from Bengaluru
