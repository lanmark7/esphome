# Security Cleanup

After rebooting it is often a lot easier to make changes over SSH instead of on the console with mini keyboard.

Connect to the device by going to the command prompt and typing in below switching out **opz2w** with whatever hostname you picked that was cool

    ssh orangepi@opz2w

In order to change the orangepi username you must first set a password for root so you can login as that account and change the other.

    sudo passwd root

Now set a password for the orangepi user so it isn't just **orangepi**

    sudo passwd

Type logout and then change your SSH command to the below changing the host name to your host name:

```bash
    ssh root@opz2w
```

Remove these two files and reboot
```bash
    rm /lib/systemd/system/getty@.service.d/override.conf
    rm /lib/systemd/system/serial-getty@.service.d/override.conf
    reboot -n
```

Then to change the usern type in the following two commands replacing 'NEW_NAME' with whatever
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
