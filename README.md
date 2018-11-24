# MQTT_NodeMCU

Arduino library for MQTT support using NodeMCU and ESP8266.

Just replace "ssid","password" and Broker(RPi) IP address with your credentials in .ino file.

Setup Raspberry Pi

1. Import Repository Package

    wget http://repo.mosquitto.org/debian/mosquitto-repo.gpg.key
  
    sudo apt-key add mosquitto-repo.gpg.key


2. Make it availalbe

    cd /etc/apt/sources.list.d/
    
    sudo wget http://repo.mosquitto.org/debian/mosquitto-jessie.list
    
    sudo apt-get update
  
3. Install MQTT server and client

    sudo apt install -y mosquitto mosquitto-clients

4. Check Successful Installation (should show active)

    systemctl status mosquitto.service 

5. Install paho-mqtt 

    sudo pip install RPi.GPIO paho-mqtt

6. You can publish data to nodeMCU

    mosquitto_pub -h raspberrypi -t "/leds/esp8266" -m "ON"
    
    mosquitto_pub -h raspberrypi -t "/leds/esp8266" -m "OFF"


Setup Arduino

1. Install "Adafruit MQTT" from "Mannge Libraries"

2. Open MQTT_NodeMCU.ino in Arduino IDE

    Replace "ssid" and "password" 
    Replace Broker(RPi) IP address
    Define "led_pin" and "sensor_input"
    
3. Upload the sketch and open Serial Monitor at 115200


Now, you can run MQTT_Pi.py (from repository) and should see sensor data on tereminal.
