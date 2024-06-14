# Security Cleanup

Remove these two files and reboot
```bash
    rm /lib/systemd/system/getty@.service.d/override.conf
    rm /lib/systemd/system/serial-getty@.service.d/override.conf
    reboot -n
```

Then to change the username, type in the following two commands replacing 'NEW_NAME' with whatever
```bash
    usermod -l NEW_NAME -d /home/NEW_NAME -m orangepi
```

After you have renamed the default user you can disable the root user by typing in this:
```bash
    sudo passwd -l root
```

You should also turn off the permit login as root here:
```bash
    sudo nano /etc/ssh/sshd_config
```

Restart the SSH service
```bash
sudo systemctl restart ssh
```
