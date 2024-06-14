# Source Repositories Update

The default apt sources for the Orange Pi are in China and so we want to update so it pulls from repositories closer to where the devices are located.  In theory the overseas images are identical through CRC/SHA checking but just is a good practice to pull data closer to home.

## Configure APT Sources

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
# See http://help.ubuntu.com/community/UpgradeNotes for how to upgrade to newer versions of the distribution.
deb http://ports.ubuntu.com/ubuntu-ports jammy main restricted
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy main restricted

## Major bug fix updates produced after the final release of the distribution.
deb http://ports.ubuntu.com/ubuntu-ports jammy-updates main restricted
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy-updates main restricted

deb http://ports.ubuntu.com/ubuntu-ports jammy universe
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy universe
deb http://ports.ubuntu.com/ubuntu-ports jammy-updates universe
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy-updates universe

deb http://ports.ubuntu.com/ubuntu-ports jammy multiverse
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy multiverse
deb http://ports.ubuntu.com/ubuntu-ports jammy-updates multiverse
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy-updates multiverse

## N.B. software
deb http://ports.ubuntu.com/ubuntu-ports jammy-backports main restricted universe multiverse
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy-backports main restricted universe multiverse

deb http://ports.ubuntu.com/ubuntu-ports jammy-security main restricted
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy-security main restricted
deb http://ports.ubuntu.com/ubuntu-ports jammy-security universe
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy-security universe
deb http://ports.ubuntu.com/ubuntu-ports jammy-security multiverse
# deb-src http://ports.ubuntu.com/ubuntu-ports jammy-security multiverse
```

## Update Software

Update the kernel:
```bash
sudo apt full-upgrade
```

Do a update and upgrade:
```bash
sudo apt update; \
  sudo apt upgrade
```

Do a kernal update:
```bash
sudo apt full-upgrade
```

Allow any held back packages to update
```bash
sudo apt dist-upgrade
```

Remove any packages no longer neeed
```bash
sudo apt autoremove
```
