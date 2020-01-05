```
临时限额增加可以设置新的指令：

sudo sysctl fs.inotify.max_user_watches = 524288 
sudo sysctl -p
```

```
永久限额增加可以设置新的指令：

echo fs.inotify.max_user_watches = 524288 | sudo tee -a /etc/sysctl.conf 
sudo sysctl -p
```

