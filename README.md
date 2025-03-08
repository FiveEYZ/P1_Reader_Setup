# P1_Reader_Setup

1. Mosquitto broker
2. Add P1Reader to wifi and MQTT



# Home Assistant Add-on: Mosquitto broker
## Installation

Follow these steps to get the add-on installed on your system:

1. Navigate in your Home Assistant frontend to **Settings** -> **Add-ons** -> **Add-on store**.
2. Find the "Mosquitto broker" add-on and click it.
3. Click on the "INSTALL" button.

## How to use

The add-on has a couple of options available. To get the add-on running:

1. Start the add-on.
2. Have some patience and wait a couple of minutes.
3. Check the add-on log output to see the result.

Create a new user for MQTT via your Home Assistant's frontend **Settings** -> **People** -> **Users** , (i.e. not on Mosquitto's **Configuration** tab).
Notes:

1. This name cannot be `homeassistant` or `addons`, those are reserved usernames.
2. If you do not see the option to create a new user, ensure that **Advanced Mode** is enabled in your Home Assistant profile.

To use the Mosquitto as a broker, go to the integration page and install the configuration with one click:

1. Navigate in your Home Assistant frontend to **Settings** -> **Devices & Services** -> **Integrations**.
2. MQTT should appear as a discovered integration at the top of the page
3. Select it and check the box to enable MQTT discovery if desired, and hit submit.


# Add P1Reader to wifi and MQTT

1. When your P1Reader starts up, it sets it up in Station mode and tries to connect to a previously saved Access Point
2. if this is unsuccessful (or no previous network saved) it moves the P1Reader into Access Point mode and spins up a DNS and WebServer (default ip 192.168.4.1)
3. using any wifi enabled device with a browser (computer, phone, tablet) connect to the newly created Access Point
4. because of the Captive Portal and the DNS server you will either get a 'Join to network' type of popup or get any domain you try to access redirected to the configuration portal
5. choose one of the access points scanned, enter password also add the user we made in Mosquitto broker then click save
6. P1Reader will try to connect. If successful, it relinquishes control back to your app. If not, reconnect to AP and reconfigure.
7. There are options to change this behavior or manually start the configportal and webportal independantly as well as run them in non blocking mode.

