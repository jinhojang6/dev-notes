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
