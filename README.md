## Handcrafted Systems

Intended for users looking for a privacy-focused, self-hosted home automation system

### Network Layer
| Name                | Purpose                       | Type      | Config             | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------------|
| Zigbee              | Sensor & trigger connectivity | Hardware  | Pass-through       | /dev/ttyACM0  |
| Zigbee2MQTT         | MQTT translation + Admin      | Container | RTP migrated       | 8290          |
| MQTT                | Pub/Sub                       | Container | RTP handcraftedsys | 1883,9001     |
| Pi-hole             | Local DNS + Ad-blocking       | Container | RTP handcraftedsys | 53            |

### Security Layer
| Name                | Purpose                       | Type      | Config             | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------------|
| acme.sh             | Local HTTPS                   | Crontab   | ~/.acme.sh /certs  | N/A           |
| Headscale           | Tailscale control server      | Container | RTP handcraftedsys | 27896,9090    |
| Tailscale           | Pi-hole Tailnet inclusion     | Service   | cmdline            | N/A           | 

### Application Layer
#### Server
| Name                | Purpose                       | Type      | Config             | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------------|
| Caddy               | Reverse-proxy                 | Service   | /etc/caddy *.caddy | 80,443        |
| Runtipi             | App store                     | Container | ~/runtipi          | 9079,9443     |
| DuckDNS             | Dynamic DNS                   | Container | RTP migrated       | N/A           | 

#### Automation
| Name                | Purpose                       | Type      | Config             | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------------|
| openHAB             | Rules, scenes, history        | Service   | /etc/openhab UI    | 8080          |
| ESPHome             | Custom IoT hardware           | TBD       | TBD                | TBD           |
| Home Assistant      | Rules, scenes, history        | TBD       | TBD                | TBD           | 

### Upcoming
| Name                | Purpose                       | Type      | Config             | Port(s)       |
|:--------------------|:------------------------------|:----------|:-------------------|:--------------|
| raspiBackup         | Scheduled back-ups            | Cron      | TBD                | TBD           |
| Apprise             | Notifications                 | Container | TBD                | TBD           |
| Uptime Kuma         | Service monitoring & alerts   | Container | TBD                | TBD           |
| TriliumNext         | Notes, diagrams & more        | Container | TBD                | TBD           |
| Authentik/Pocket-ID | OIDC provider                 | TBD       | TBD                | TBD           |
| Keepalived          | High-availability             | Service   | TBD                | TBD           |


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
