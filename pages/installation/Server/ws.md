# `ws-server` Setup Guide

The `ws-server` can be run in two different ways, depending on your setup requirements:

---

## Option 1: Run as a FiveM Resource

The `ws-server` can be hosted directly within your existing FiveM server or on a separate FiveM server. Both approaches are supported.

1. **Download the server**
   Download the latest release of `ws-server` from the [GitHub Releases page](https://github.com/Plactrix/TokoVoIP_v2/releases/latest).

2. **Extract the files**
   Place the extracted `ws-server` folder into the `resources` directory of your FiveM server.

3. **Configure the server**
   Open the configuration file: [`ws_server/config.js`](https://github.com/Plactrix/TokoVoIP_v2/blob/master/ws_server/config.js)
   Set the `TSServer` value to the **IPv4 address** of your TeamSpeak server.

4. **Start the server**
   Start the `ws_server` from your FiveM server console using the appropriate `start` command.

5. **Save the WebSocket address**
   Once started, the console will display a message such as `Listening on IP:PORT`.
   Copy this value and save it for use in [Step 2: Setting up the tokovoip\_script](#step-2-setting-up-tokovoip_script).

---

## Option 2: Run as a Standalone Node.js Application

The `ws-server` can also be run as an independent Node.js application. This is useful if you want to separate it from the FiveM runtime.

1. **Install Node.js**
   Download and install the latest version of [Node.js](https://nodejs.org/en/).

2. **Configure the server**
   Open the configuration file: [`ws_server/config.js`](https://github.com/Plactrix/TokoVoIP_v2/blob/master/ws_server/config.js)

   * Set the `TSServer` value to your TeamSpeak server's **IPv4 address**.
   * If hosting on a separate machine, ensure the `ws-server` is accessible by the FiveM server.

3. **Install dependencies and start the server**

   Open a terminal or command prompt in the `ws-server` directory and run the following commands:

   ```bash
   npm install
   node index.js
   ```

4. **(Optional) Run in the background**

   To keep the server running continuously, use a process manager such as:

   * [`pm2`](https://pm2.keymetrics.io/)
   * `screen` (Linux-only)
   * `systemd` (Linux-only)
