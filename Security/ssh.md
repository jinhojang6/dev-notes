## Changing the default SSH port
```
// backup
cp  /etc/ssh/sshd_config  /etc/ssh/sshd_config_backup 
vim /etc/ssh/sshd_config

// Change 
#Port 22
to 
Port {new SSH port} 
sudo service sshd restart

// Test
ssh username@userIP -p 49160
```

- https://linuxhint.com/change_default_ssh_port/

<br />

## Activate an SSH daemon
```
sudo service ssh start

# Check
sudo netstat -anp | grep LISTEN | grep sshd
```

<br/>

## Permissions 0664 for 'key.pem' are too open. It is required that your private key files are NOT accessible by others.
```
sudo chmod 600 /path/to/my/key.pem
```
- Reference: https://stackabuse.com/how-to-fix-warning-unprotected-private-key-file-on-mac-and-linux/
