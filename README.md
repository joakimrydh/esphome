# esphome
## Settings and stuff related to esphome connected to home assistant
<br>

### Xiaomi Thermometer
https://www.aliexpress.com/item/4001110925366.html?spm=a2g0s.9042311.0.0.17b64c4d2ZlN76

To flash the thermometer:
1. download the file "ATC_Thermometer.bin" from: https://github.com/atc1441/ATC_MiThermometer
2. Flash the xiaomi ble temp sensors using this page: https://atc1441.github.io/TelinkFlasher.html

After flashing is done, select the settings you want:

Settings I use:
- <b>Advertising type must be set as custom.</b>
- Smiley off
- Battery icon disabled
- 10 seconds report time

### esp32
Connect and prepare an esp32 according to the esphome documentation.

In the file xiaomi_ble_relay_esp32.yaml:
- Set the devicename variable to the name you want for the node.
- Set the ssid and password of your WiFi in the wifi section.
- Set the correct broker IP, MQTT username and MQTT password in the mqtt section

Flash the file on the esp32 device.

### Home Assistant
The sensors needs to be manually configured in Home Assistant.
<br>
Use the info in ha_sensor_config.yaml to configure the sensors; edit the name of the devices as well as the MAC address in the mqtt topic. The MAC adress always starts with "A4:C1:38" and the last three bytes are shown on the thermometer display when it starts up.
<br>
Reload MQTT sensors or restart Home Assistant to add the sensors.
