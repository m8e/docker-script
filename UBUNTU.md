# Config for Docker on Ubuntu Server  

NOTE: all theses command are executed as root : `sudo su -`

## Limit the SWAP  
Did you ever see the message **WARNING: No swap limit support** when you type `docker info` ?  
You have to make the swap accountable to resolve that;  

1' Add this `cgroup_enable=memory swapaccount=1` at that line `GRUB_CMDLINE_LINUX="` in the file `/etc/default/grub`  

which result on something like this :  
```
GRUB_CMDLINE_LINUX="cgroup_enable=memory swapaccount=1"
```
2' update your grub  
```
update-grub
reboot
```

## Make Docker daemon more secure than by default
ref: https://docs.docker.com/engine/reference/commandline/dockerd/

1' Open the file `/etc/systemd/system/multi-user.target.wants/docker.service`  
than find the line which start with `ExecStart=`  

### WARNING
- Even if you already have containers running; `icc` and `no-new-privileges` are relatively safe to add.  
- `userns-remap` will make docker running as user instead of root.  
This option will require, at least a migration of your actual containers.  

which result on something like this :  
```
ExecStart=/usr/bin/dockerd --icc=false --no-new-privileges -H fd://  
```

2' Restart your docker daemon  
```
systemctl daemon-reload
systemctl restart docker
```
