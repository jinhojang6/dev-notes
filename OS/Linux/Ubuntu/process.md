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

## Kill or terminate an inactive or idel ssh session
```
pstree -p | grep sshd
kill -9 {pid}
```
- https://www.2daygeek.com/kill-terminate-inactive-idle-ssh-session-on-linux/

<br />