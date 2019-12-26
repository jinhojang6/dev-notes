## Check OS version
```
cat /etc/os-release
lsb_release -a
hostnamectl
```

## Find files
```
find /home/username/ -name "*.err"
find -iname "filename"

references: 
https://www.linode.com/docs/tools-reference/tools/find-files-in-linux-using-the-command-line/
https://www.wikihow.com/Find-a-File-in-Linux
```

## Check PID by port
```
sudo ss -lptn 'sport = :80'
```

## Kill process by PID
```
sudo kill-9 [pid]
```