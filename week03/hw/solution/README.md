# Homework 3 - Internet of Things 101

# jetson setup

facedetector => IoT Hub => forwarder 

### Face detector 
Placeholder 

- cuda ubuntu with OpenCV
- publish images to IoT Hub

```
# Create a bridge:
docker network create --driver bridge hw03
```

### IoT Hub 

```
# Create an alpine linux - based mosquitto container:
docker run --name mosquitto --network hw03 -p 1883:1883 -ti alpine sh
# we are inside the container now
# install mosquitto
apk update && apk add mosquitto
# run mosquitto
/usr/sbin/mosquitto
```

### Forwarder 

Read from mosquitto broker and submit to Cloud 

```
mosquitto_sub -t test_topic -h mosquitto_iot_hub
```



