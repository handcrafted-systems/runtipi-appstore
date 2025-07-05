## Handcrafted Systems

Intended for users looking for a privacy-focused, self-hosted home automation system

### Hardware Layer
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Raspberry Pi 5 Rec. | Accessible, mid-spec hub      | SBC       | raspi-config       | Both    | Eth/WiFi+USB  |
| Zigbee              | Sensor & trigger connectivity | Dongle    | Pass-through       | N/A     | /dev/ttyACM0  |
| Raspberry Pi 0 2W   | Core services fallback hub    | SBC       | dietpi             | CLI     | WiFi          |
| Mini PC Opt.        | High-spec & -cost hub         | SBC       | Proxmox            | Both    | Eth/WiFi+USB  |

### Network Layer
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Zigbee2MQTT         | MQTT translation + Admin      | Container | handcraftedsys     | GUI     | 8290          |
| MQTT                | Pub/Sub                       | Container | handcraftedsys     | N/A     | 1883,9001     |
| Pi-hole             | Local DNS + Ad-blocking       | Container | handcraftedsys     | GUI     | 8081          |

### Security Layer
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| acme.sh             | Local HTTPS                   | Crontab   | ~/.acme.sh /certs  | CLI     | N/A           |
| Headscale           | Tailscale control server      | Container | handcraftedsys     | CLI*    | 27896,9090    |
| Tailscale           | Pi-hole Tailnet inclusion     | Service   | cmdline            | CLI     | N/A           |

<sup>* GUI to be added (Headplane / Headscale-UI)</sup>

### Application Layer
#### Server
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Caddy               | Reverse-proxy                 | Service   | /etc/caddy *.caddy | GUI     | 80,443        |
| Runtipi             | App store                     | Container | ~/runtipi          | Both    | 9079,9443     |
| DuckDNS             | Dynamic DNS                   | Container | handcraftedsys     | N/A     | N/A           |

#### Content
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Apprise             | Notifications                 | Container | handcraftedsys     | Both    | 8000          |
| Uptime Kuma         | Service monitoring & alerts   | Container | handcraftedsys     | GUI     | 8125          |
| TriliumNext         | Notes, diagrams & more        | Container | handcraftedsys     | GUI     | 8267          |

#### Automation
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| openHAB             | Rules, scenes, history        | Service   | /etc/openhab       | Both*   | 8080          |
| ESPHome             | ESP32-based sensors/triggers  | TBD       | TBD                | TBD     | TBD           |
| Home Assistant      | Rules, scenes, history        | TBD       | TBD                | TBD     | TBD           |

<sup>*Karaf console only accessible via CLI</sup>

### Upcoming
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| raspiBackup         | Scheduled back-ups            | Cron      | TBD                | CLI     | TBD           |
| Authentik/Pocket-ID | OIDC provider                 | Container | handcraftedsys     | GUI     | 8387          |
| Keepalived          | High-availability             | Service   | TBD                | CLI     | TBD           |
| HomeBox             | Organising & tracking         | Container | handcraftedsys     | GUI     | TBD           |
| Syncthing           | P2P file syncing              | Container | handcraftedsys     | GUI     | TBD           |


## Installation

1. In the Runtipi dashboard, open `Settings` and go to the `App Stores` tab.
2. Click `Add App Store`, fill in the form with `handcraftedsys` and the URL `https://github.com/handcrafted-systems/runtipi-appstore` then click `Submit`
3. You can now go to the `App Store` page and select the one you just created from the dropdown.

Follow the Documentation below for next steps!

## Documentation

Coming soon!

## Repository Structure

- **apps/**: Contains individual app directories

  - Each app has its own folder (e.g., `whoami/`) with the following structure:
    - `config.json`: App configuration file
    - `docker-compose.json`: Docker setup for the app
    - `metadata/`: Contains app visuals and descriptions
      - `description.md`: Markdown description of the app
      - `logo.jpg`: App logo image

- **tests/**: Contains test files for the app store

  - `apps.test.ts`: Test suite for validating apps
