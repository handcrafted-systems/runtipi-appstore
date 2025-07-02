## Handcrafted Systems Runtipi App Store

Intended for users looking to have a self-hosted home automation system

### Network Layer
| Name             | Type     | Config             | Port(s)       |
|------------------|----------|--------------------|---------------|
|  Zigbee          | Hardware | Pass-through       | /dev/ttyACM0  |
|  Zigbee2MQTT     | Docker   | RTP migrated       | 8290          |
|  MQTT            | Docker   | RTP handcraftedsys | 1883          |

### Automation Layer
| Name             | Type     | Config             | Port(s)       |
|------------------|----------|--------------------|---------------|
| openHAB          | Service  | /etc/openhab UI    | 8080          |
| ESPHome          | TBD      | TBD                | TBD           |
| Home Assistant   | TBD      | TBD                | TBD           |

### Application Layer
| Name             | Type     | Config             | Port(s)       |
|------------------|----------|--------------------|---------------|
| Caddy            | Service  | /etc/caddy *.caddy | 80,443        |
| Pi-hole          | Docker   | RTP handcraftedsys | 53            |        

### Security Layer
| Name             | Type     | Config             | Port(s)       |
|------------------|----------|--------------------|---------------|
| acme.sh          | Crontab  | ~/.acme.sh /certs  | N/A           |
| Headscale        | Docker   | RTP handcraftedsys | 27896,9090    |
| Tailscale        | Service  | cmdline            | N/A           |

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
