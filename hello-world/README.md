# Hello world

## Build

```bash
export APP_NAME=hello-world
# The AXIS_TARGET_IP variable needs to be changed to your device's IP
export AXIS_TARGET_IP=<actual camera IP address>

docker build . -t $APP_NAME

# If TLS activated:
docker save $APP_NAME | docker --tlsverify -H tcp://$AXIS_TARGET_IP:2376 load

# If TLS not activated:
docker save $APP_NAME | docker -H tcp://$AXIS_TARGET_IP load
```

## Run

```bash
# If TLS activated:
docker --tlsverify -H tcp://$AXIS_TARGET_IP:2376 run -it $APP_NAME

# If TLS not activated:
docker -H tcp://$AXIS_TARGET_IP run -it $APP_NAME
```