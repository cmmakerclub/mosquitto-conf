# Mosquitto MQTT Broker & Bridging

## preparation
	$ cd $HOME
	$ git clone https://github.com/cmmakerclub/mosquitto-conf.git

	
# for x86
	docker run -it -p 1883:1883 -p 9001:9001 -v $HOME/mosquitto-conf/config:/mosquitto/config -v /mosquitto/data -v /mosquitto/log eclipse-mosquitto:1.4.12

# for raspberry pi
	export MOUNT_CONF_DIR=$HOME/mosquitto-conf/config:/mqtt/config
	export MOUNT_LOG_DIR=$HOME/mosquitto-conf/log:/mosquitto/log
	export MOUNT_DATA_DIR=$HOME/mosquitto-conf/data:/mosquitto/data
	docker run --user $(id -u) --rm -it -p 1883:1883 -p 9001:9001 \
	-v ${MOUNT_DATA_DIR} \
	-v ${MOUNT_LOG_DIR}  \
	-v ${MOUNT_CONF_DIR}:ro sbiermann/rpi-mosquitto