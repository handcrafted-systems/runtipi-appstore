# Eclipse Mosquitto MQTT Broker

## Eclipse Mosquitto

[Eclipse Mosquitto](https://mosquitto.org/) is an open source (EPL/EDL licensed) message broker that implements the MQTT protocol versions 5.0, 3.1.1 and 3.1. Mosquitto is lightweight and is suitable for use on all devices from low power single board computers to full servers.

Mosquitto is part of the [Eclipse Foundation](https://eclipse.org/), and is an [iot.eclipse.org project](https://iot.eclipse.org/). The development is driven by Cedalo.

The broker is configured by default that it listens to the port **1883** for tcp connections.
To also use websocket connection you can enable it by edit the `/runtipi/app-data/app-store-name/eclipse-mosquitto/data/config/mosquitto.conf` with the following content:

```
listener 9001
protocol websockets
```

**Note**
WebSockets, while powerful, can introduce vulnerabilities if left unsecured. They should be secured using TLS/encryption.
For more detailed information the [mosquitto documentation](https://mosquitto.org/man/mosquitto-conf-5.html). 

### See the man page for MQTT Authentication methods here:

- Mosquitto documentation: [https://mosquitto.org/documentation/authentication-methods/](https://mosquitto.org/documentation/authentication-methods/)


## Links

### See the following links for more information on MQTT:

- Community page: [http://mqtt.org/](http://mqtt.org/)
- MQTT v3.1.1 standard: [https://docs.oasis-open.org/mqtt/mqtt/v3.1.1/mqtt-v3.1.1.html](https://docs.oasis-open.org/mqtt/mqtt/v3.1.1/mqtt-v3.1.1.html)
- MQTT v5.0 standard: [https://docs.oasis-open.org/mqtt/mqtt/v5.0/mqtt-v5.0.html](https://docs.oasis-open.org/mqtt/mqtt/v5.0/mqtt-v5.0.html)

### Mosquitto project information is available at the following locations:

- Main homepage: [https://mosquitto.org/](https://mosquitto.org/)
- Find existing bugs or submit a new bug: [https://github.com/eclipse/mosquitto/issues](https://github.com/eclipse/mosquitto/issues)
- Source code repository: [https://github.com/eclipse/mosquitto](https://github.com/eclipse/mosquitto)

There is also a public test server available at [https://test.mosquitto.org/](https://test.mosquitto.org/)
