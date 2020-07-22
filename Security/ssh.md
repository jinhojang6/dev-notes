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
