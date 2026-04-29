> [!WARNING]
> **UNTESTED / IN-DEVELOPMENT**
> This plugin is currently in active development and has not been fully tested in a production environment. Use at your own risk.

# Biamp Tesira Control Plugin for Q-SYS

This plugin provides control for Biamp Tesira DSPs over the Tesira Text Protocol (TTP).

## Features
- Switchable connection modes (TCP or RS-232)
- Dynamic channel generation based on properties
- Dedicated Mute-only channel blocks
- Auto-Mute logic (Mutes when volume hits minimum)
- Auto-Unmute logic (Unmutes when volume raised from mute)
- Smooth Volume Ramping controls
- Clean UI with explicit mapping in settings

## How to Use
1. Add the plugin to your schematic and configure the number of **Level + Mute** and **Mute Only** controls in the Properties pane.
2. Select your connection type (`TCP` or `RS-232`). If using TCP, enter the **IP Address** of the Biamp processor in the properties.
3. Open the plugin's control panel and go to the **Settings** tab to map your DSP blocks.

### Mapping Example
To control the first channel of a standard Level block named "Level1" in Biamp:
- **Label**: `Mic 1` *(This is just for your UI, it can be whatever you want)*
- **Instance Tag**: `Level1` *(The exact instance tag of the block in your Tesira configuration)*
- **Index**: `1` *(The specific channel number inside that block)*

For a matrix block or custom block, the index may need row/column format (e.g., `1 1`).

*Note: The plugin automatically manages the connection and will refresh its block subscriptions automatically every 5 minutes in the background to ensure states stay perfectly synced.*

## Author
Dustin Bennett
