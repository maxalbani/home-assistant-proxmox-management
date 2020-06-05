# home-assistant-proxmox-management
A custom Proxmox console on Home Assistant to manage VM &amp; LXC, made with Node-Red.

## Features

 - Get VM & LXC Container info
 - Start VM & LXC
 - Shutdown VM & LXC
 - Reboot VM & LXC
 - Create Snapshot

## Requirements

This components are required for installation:

 - [Official Home Assistant PROXMOX VE integration](https://www.home-assistant.io/integrations/proxmoxve/)  
 - [Custom component Variables](https://github.com/snarky-snark/home-assistant-variables)
 - [Mosquitto broker Add-on](https://github.com/home-assistant/hassio-addons/tree/master/mosquitto) (MQTT)
 - [Node-Red Add-on](https://github.com/hassio-addons/addon-node-red)
 - [Packages configuration](https://www.home-assistant.io/docs/configuration/packages/)
 
 ## Installation

**Before proceeding with the installation, make sure you have installed and configured all the required components!**

The logic of node-red flows is based on the presence of **binary sensors** created by the **Proxmox VE integration**.
For example, with this configuration you will have **four** binary sensors:

```yaml
proxmoxve:
  - host: 192.168.x.x
    username: hass
    password: fake
    verify_ssl: false
    realm: pve
    nodes:
      - node: pve
        vms:
          - 100
          - 102
          - 103
        containers:
          - 101
```


