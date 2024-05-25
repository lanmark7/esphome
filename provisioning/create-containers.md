# Create Containers

Now that everything is installed you can now start creating your containers like ESPHome, Home Assistant, RabbitMQ or MQTT

I personally like putting my docker stuff in the /media path.   Since docker runs as root we need to first switch to a root context:

```bash
sudo -i
```

Create a docker folder under /media:
```bash
mkdir docker
```

While you are at it create the following folders under the /media/docker:

* esphome
* homeassistant
* rabbitmq

Under each of these folder create a place to keep container files in a persistent place so when we update containers we still have the app data

* volumes

so you now should have the following paths:

* /media/docker/esphome/volumes
* /media/docker/homeassistant/volumes
* /media/docker/rabbitmq/volumes

If you look in this Git repo there is a root folder called docker that shows this folder structure as well as docker-compose.yaml files to get you started.