# Changelog MQTT Manager

>**IMPORTANT**
>
>As a reminder, if there is no information on the update, it is because it concerns only the update of documentation, translation or text.

- Added a global configuration window for the transmission of equipment between Jeedom

# 08/08/2024

- For equipment transmitted on Mqtt the plugin now sends the battery level every night
- The plugin to manage the battery level transmitted between Jeedom
- Correct management of refresh commands on widgets on equipment transmitted between Jeedom
- When sending the discovery between Jeedom the values of the commands are also transmitted (no need to wait for an update of the value to have it on the target). Requires resend discovery
- When transmitting equipment between Jeedom the plugin now manages the real type of equipment to be compatible with mobile applications. Requires resend discovery

# 05/08/2024

- With Jeedom 4.4.8 or more possibility of no longer sending all the equipment on the MQTT brocker but only certain ones (to be configured in the advanced configuration of the equipment to be transmitted)
- Bug fixes (especially for php8 compatibility)
- Discovery between Jeedom (to make 2 jeedoms communicate with each other by mqtt)
- Possibility from the plugin configuration page to delete the subscription of a plugin

# 03/22/2024

- Fixed a problem under php8
- Fixed a bug under Debian 12

# 02/23/2024

- Deleting a launchable daemon check (done when launching the daemon in all cases)

# 01/15/2024

- Preparing for jeedom 4.4
- Improved mosquitto management under Docker

# 10/27/2023

- Fixed a bug on the state of the daemon (started when not)

# 05/10/2023

- Fixed a bug on brocker status

# 02/10/2023

- Possibility to correct the default QOS
- Bugfix
- Start of adding the auto discovery system
- Improved mosquitto handling in local mode

# 03/22/2023

- Bugfix

# 07/03/2023

- Addition of an autodiscovery system for some beta modules (esphome, tasmota and shelly)
- Added the image of the modules
- Fixed a bug on the client ID (if several jeedom on the same broker)
- Sub-level support in equipment topics
- Bug fix

# 23/12/2022

- Fixed a bug on the maximum time allowed for installing dependencies
- Added equipment template system (beta)

# 11/18/2022

- Added a message prompting to restore permissions on folders before installing Mosquitto in case of error **No SSL folder found**

# 11/13/2022

- Added a button to uninstall a local Mosquitto broker on the general plugin configuration page
