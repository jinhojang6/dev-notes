## Poppular Linux commands
```
- https://www.ubuntupit.com/best-linux-commands-to-run-in-the-terminal/
- https://www.howtogeek.com/412055/37-important-linux-commands-you-should-know/
```

<br />

## Check OS version
```
cat /etc/os-release
lsb_release -a
hostnamectl
```

<br />

## Find files
```
find /home/username/ -name "*.err"
find -iname "filename"

references: 
https://www.linode.com/docs/tools-reference/tools/find-files-in-linux-using-the-command-line/
https://www.wikihow.com/Find-a-File-in-Linux
```

<br />

## Find directories
```
find . -type d -name backups (find a directory named `backups` in the current folder)
find . -type d -name backups -ls (mored detailed info)

references: 
https://www.cyberciti.biz/faq/howto-find-a-directory-linux-command/
```

<br />

## Check PID by port
```
sudo ss -lptn 'sport = :{port}'
e.g., sudo ss -lptn 'sport = :80'
```

<br />

## Kill process by PID
```
sudo kill -9 [pid]
```

<br />

## Recent ssh session logs
```
# Successful connection
w
last

# Failed connection
sudo last -f /var/log/btmp
```

<br />

## Kill or terminate an inactive or idel ssh session
```
pstree -p | grep sshd
kill -9 {pid}
```
- https://www.2daygeek.com/kill-terminate-inactive-idle-ssh-session-on-linux/

<br />

## Change password
```
sudo passwd {username}
```
- https://www.cyberciti.biz/faq/change-a-user-password-in-ubuntu-linux-using-passwd/

<br />

## Delete all files in the current directory
```
rm *
rm -r * (including subdirectories and files inside them)
```

<br />

## Run a .sh file
```
chmod +x /path/to/yourscript.sh
/path/to/yourscript.sh
```

<br/>

## Tail log files
Check recent logs
```
tail -f /path/to/log/file
```
Last 100 lines
```
tail -n 100 /path/to/log/file
```
