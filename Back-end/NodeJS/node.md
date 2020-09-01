## Delete the current version and install node 12.x 
```
sudo apt-get purge nodejs
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt install nodejs
```

<br/>

## Update to the latest stable version
```
sudo npm install -g n
sudo n stable
sudo n 10.16.0
```

<br/>

## Increasing the amount of inotify watchers

You can set a new limit temporary with:
```
sudo sysctl fs.inotify.max_user_watches=524288
sudo sysctl -p
```

If you like to make your limit permanent, use:
```
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf
sudo sysctl -p
```

- [Solution](https://github.com/guard/listen/wiki/Increasing-the-amount-of-inotify-watchers#the-technical-details)
- [Error: ENOSPC: System limit for number of file watchers reached](https://github.com/gatsbyjs/gatsby/issues/11406)
