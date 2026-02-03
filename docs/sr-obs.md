# OBS WebSocket Setup Guide

This guide walks you through setting up OBS WebSocket and connecting it to StreamRoll’s OBS events.

## 1) Install/Enable OBS WebSocket

1. Open OBS Studio.
2. Open the **Tools** menu.
3. If you see **WebSocket Server Settings**, continue to step 2.
4. If you do not see it, install the OBS WebSocket plugin for your OBS version, then restart OBS.

> Note: StreamRoll expects a local WebSocket connection and uses **ws://**.

## 2) Configure WebSocket Server Settings

1. In OBS, go to **Tools → WebSocket Server Settings**.
2. Ensure **Enable WebSocket server** is checked.
3. Set a port (default is often **4455**).
4. (Optional) Set a password.
5. Click **Apply** or **OK**.

## 3) Add the Overlay in OBS

1. In OBS, add a **Browser Source**.
2. Paste your StreamRoll overlay URL into the URL field.
3. Ensure the browser source is visible in your scene.

This step is required because StreamRoll sends the connection test through the overlay client.

## 4) Configure StreamRoll Options

1. Open your StreamRoll **Options** page.
2. In **OBS Websocket**, enter the **Socket URL** as:
   - `IP:PORT` (example: `127.0.0.1:4455`)

> Note: If the URL doesn't work from the one shown in OBS, try 127.0.0.1 with your port.

3. Enter the password if you set one.
4. Click **Test and Save Connection**.

If successful, you should see a confirmation message.

## 5) Verify Event Triggers

1. Create or edit a dice config.
2. Add an **OBS Socket** event (Source Toggle or Scene Toggle).
3. Roll the dice to confirm OBS responds.

## Troubleshooting

- **“Failed to connect”**
  - Ensure the overlay is open in OBS and visible.
  - Verify the IP and port match OBS WebSocket settings.
  - Confirm OBS WebSocket server is enabled.

- **Password issues**
  - Re-check the password in OBS and StreamRoll.

- **No OBS response**
  - Confirm the Scene/Source names match exactly in OBS.

## Example Values

- Socket URL: `127.0.0.1:4455`
- Password: (your chosen password)

---

If you still have issues, restart OBS and refresh the overlay, then re-test the connection.
