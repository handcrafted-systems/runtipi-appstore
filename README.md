## Handcrafted Systems Runtipi App Store

Intended for users looking to have a self-hosted home automation system based on:

- Network Layer
  
  - Zigbee
  - Zigbee2MQTT
  - MQTT

- Automation Layer

  - openHAB
  - ESPHome
  - Home Assistant

- Application Layer

  - Caddy
  - Pi-hole

- Privacy Layer

  - Headscale
  - Tailscale

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
