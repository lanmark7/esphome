# File Shares

 Being able to backup the various files on the device as well as drop updated files directly on the device is important.

 The implementation we will be using is called Samba.

 NOTE: if you don't need to use mapped network drives and robocopy and such it is probably a lot safer security wise to use Filezilla and connect using sftp (which is SSH file transfer).
 

External Reference:
* [How to install and configure Samba](https://linuxize.com/post/how-to-install-and-configure-samba-on-ubuntu-18-04/)


## Basic Install

Always good to make sure we have the latest apt package definitions:
 ```bash
 sudo apt update
 ```

Install the Samba packages:
 ```bash
 sudo apt install samba
 ```

 If you have a firewall running you will need to allow incoming traffic on UDP ports 137 and 138 and TCP connections on 139 and 445:
```bash
sudo ufw allow 'Samba'
```

You can check to see if Samba service is running by typing in this:
```bash
sudo systemctl status smbd
```

