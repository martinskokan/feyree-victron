# EV Charger Integration Guide

## Overview
This guide provides comprehensive instructions for integrating EV chargers.

## Prerequisites
- Basic knowledge of Home Assistant
- Installed Mosquitto broker

## Mosquitto Bridge Configuration
1. Open Mosquitto configuration file.
2. Add the necessary bridge configuration:
   ```
   # Bridge configuration
   bridge_address your_bridge_address
   bridge_username your_username
   bridge_password your_password
   ```

## Home Assistant Setup
To set up the integration in Home Assistant, follow these steps:

1. Go to Configuration > Integrations.
2. Click on + Add Integration and search for "EV Charger".
3. Follow prompts to set up with these automations:
   ### Automation 1: Battery Level
   - Triggers: Charge level changes
   - Actions: Notify user if below 20%
   ### Automation 2: Charging Status
   - Triggers: Charge status changes
   - Actions: Update status in UI
   ### Automation 3: Surge Protector
   - Activate upon surge warnings.
   ### Automation 4: Consumption Monitoring
   - Log consumption data every hour.
   ### Automation 5: Charging Schedule
   - Enable charging between specified times.

## Node-RED Surplus Charging Flow
To create a surplus charging flow in Node-RED, use the following:
1. Drag in an MQTT node for the charger.
2. Set the payload to "charging" when surplus detected.
3. Monitor and control charging times.

## MQTT Topic Reference
- `ev/charger/status`: Current status of the charger.
- `ev/charger/data`: Data from the charger.

## Troubleshooting Guide
1. Check log files for any errors.
2. Ensure the Mosquitto bridge is correctly configured.
3. Update Home Assistant and dependencies regularly.

## Deployment Checklist
- Ensure all configurations are backed up.
- Verify network connectivity.

## References
- [Home Assistant Documentation](https://www.home-assistant.io/docs/)
- [Mosquitto Documentation](https://mosquitto.org/documentation/)