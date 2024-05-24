# Container Runtime

Leveraging containers makes things a lot easier to keep organized and update quickly and easily.  If not installing the Azure IoT Edge service, you should at least install the moby container runtime:

Update the APT packages to include microsoft ones:
```bash
wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb
```

Install the open source container runtime:
```bash
sudo apt-get update; \
  sudo apt-get install moby-engine moby-cli
```

To prevent container logs from filling yup your microSD card change logging to log local:

```bash
sudo nano /etc/docker/daemon.json
```
Add or change the file to look like this:
```json
{
    "log-driver": "local"
}
```

We also need to give our user permissions to talk with the docker.sock

```bash
sudo usermod -a -G docker $USER
```

Restart container engine:
```bash
sudo systemctl restart docker
```

## Docker Compose 

I personally like docker compose as it allows me to have config files that I persist and share with others making configurations easier.

```bash
sudo apt install docker-compose
```