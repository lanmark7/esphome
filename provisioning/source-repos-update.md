## Source Repositories Update

The default apt sources for the Orange Pi are in china and so we want to update so it pulls from repositories closer to where the devices are located.  In theory the overseas images are identical through CRC/SHA checking but just is a good practice to pull data closer to home.

### Configure APT Sources

Edit the sources file:
```bash
sudo nano /etc/apt/sources.list
```

Original lines:
```bash
deb http://repo.huaweicloud.com/ubuntu-ports/ jammy main restricted universe multiverse
#deb-src http://repo.huaweicloud.com/ubuntu-ports/ jammy main restricted universe multiverse

deb http://repo.huaweicloud.com/ubuntu-ports/ jammy-security main restricted universe multiverse
#deb-src http://repo.huaweicloud.com/ubuntu-ports/ jammy-security main restricted universe multiverse

deb http://repo.huaweicloud.com/ubuntu-ports/ jammy-updates main restricted universe multiverse
#deb-src http://repo.huaweicloud.com/ubuntu-ports/ jammy-updates main restricted universe multiverse

deb http://repo.huaweicloud.com/ubuntu-ports/ jammy-backports main restricted universe multiverse
#deb-src http://repo.huaweicloud.com/ubuntu-ports/ jammy-backports main restricted universe multiverse
```

Comment out the original lines and add these:
```bash
deb http://archive.ubuntu.com/ubuntu/ jammy main restricted universe multiverse
# deb-src http://archive.ubuntu.com/ubuntu/ jammy main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ jammy-updates main restricted universe multiverse
# deb-src http://archive.ubuntu.com/ubuntu/ jammy-updates main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ jammy-security main restricted universe multiverse
# deb-src http://archive.ubuntu.com/ubuntu/ jammy-security main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ jammy-backports main restricted universe multiverse
# deb-src http://archive.ubuntu.com/ubuntu/ jammy-backports main restricted universe multiverse

deb http://archive.canonical.com/ubuntu/ jammy partner
# deb-src http://archive.canonical.com/ubuntu/ jammy partner
```
