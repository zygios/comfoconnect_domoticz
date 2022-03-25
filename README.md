# Install
sudo apt install python3-pip
pip3 install pycomfoconnect
pip3 install paho-mqtt

edit /home/comfoconnect/mqtt_to_node_red.py to set IP address

To get device_uuid need to run command:
python3 /home/comfoconnect/mqtt_to_node_red.py -d <ip-address>

# comfoconnect_domoticz
Zehnder Q350 ventilation unit MQTT to Domoticz

This is a mod for the python library that michael arnauts has written on https://github.com/michaelarnauts/comfoconnect/ so that it would work together with any MQTT enabled smart home software (openhab in my case).

Information using MQTT and Node-Red is push to Domoticz, at moment also from Domoticz can control Zehnder speeds.

# Creating service in unix
Use commad:
sudo nano /lib/systemd/system/confoconnect.service (add text from file confoconnect.service)

sudo chmod 644 /lib/systemd/system/conficonnect.service
sudo systemctl daemon-reload
sudo systemctl enable conficonnect.service

//to run script manualy python3 use command:
python3 /home/comfoconnect/mqtt_to_node_red.py >> /home/comfoconnect/comfoconnect_gateway.log &

//to start service use command:
systemctl start confoconnect
systemctl stop confoconnect
