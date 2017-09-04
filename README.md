# Mosquitto MQTT Broker & Bridging

## preparation
	$ cd $HOME
	$ git clone 
	
# for raspberry pi
	docker run -it -p 1883:1883 -p 9001:9001 -v $HOME/mosquitto-conf/config:/mosquitto/config -v /mosquitto/data -v /mosquitto/log eclipse-mosquitto:1.4.12

# for x86
	docker run -it -p 1883:1883 -p 9001:9001 -v $HOME/mosquitto-conf/config:/mosquitto/config -v /mosquitto/data -v /mosquitto/log sbiermann/rpi-mosquitto