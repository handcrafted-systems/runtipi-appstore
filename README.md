## Handcrafted Systems

Intended for users looking for a privacy-focused, self-hosted home automation system

### Network Layer
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Zigbee              | Sensor & trigger connectivity | Hardware  | Pass-through       | N/A     | /dev/ttyACM0  |
| Zigbee2MQTT         | MQTT translation + Admin      | Container | RTP handcraftedsys | GUI     | 8290          |
| MQTT                | Pub/Sub                       | Container | RTP handcraftedsys | N/A     | 1883,9001     |
| Pi-hole             | Local DNS + Ad-blocking       | Container | RTP handcraftedsys | GUI     | 8081          |

### Security Layer
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| acme.sh             | Local HTTPS                   | Crontab   | ~/.acme.sh /certs  | CLI     | N/A           |
| Headscale           | Tailscale control server      | Container | RTP handcraftedsys | CLI*    | 27896,9090    |
| Tailscale           | Pi-hole Tailnet inclusion     | Service   | cmdline            | CLI     | N/A           |

<sub><sup>* GUI to be added (Headplane / Headscale-UI)</sup></sub>

### Application Layer
#### Server
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| Caddy               | Reverse-proxy                 | Service   | /etc/caddy *.caddy | GUI     | 80,443        |
| Runtipi             | App store                     | Container | ~/runtipi          | GUI     | 9079,9443     |
| DuckDNS             | Dynamic DNS                   | Container | RTP handcraftedsys | N/A     | N/A           |
| Apprise             | Notifications                 | Container | RTP handcraftedsys | Both    | 8000          |
| Uptime Kuma         | Service monitoring & alerts   | Container | RTP handcraftedsys | GUI     | 8125          |

#### Automation
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| openHAB             | Rules, scenes, history        | Service   | /etc/openhab       | Both    | 8080          |
| ESPHome             | Custom IoT hardware           | TBD       | TBD                | TBD     | TBD           |
| Home Assistant      | Rules, scenes, history        | TBD       | TBD                | TBD     | TBD           |

### Upcoming
| Name                | Purpose                       | Type      | Config             | UI      | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------|:--------------|
| raspiBackup         | Scheduled back-ups            | Cron      | TBD                | CLI     | TBD           |
| TriliumNext         | Notes, diagrams & more        | Container | TBD                | GUI     | TBD           |
| Authentik/Pocket-ID | OIDC provider                 | TBD       | TBD                | GUI     | TBD           |
| Keepalived          | High-availability             | Service   | TBD                | CLI     | TBD           |


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

## Documentation

Coming soon!
