# A little guide about subUID and subGID

I will try to explain the concept if subordinate uid/gid by example. In my example I will use (linuxserver/nextcloud)[https://hub.docker.com/r/linuxserver/nextcloud/] with docker in a userspace. This explanation my also help to understand the concept of subordinate UID/GID in general which is not tight specifically to docker and containerization.  

## Docker daemon and userns-remap
As you must know; when a process run in a userspace (as a user), in that case it is dockerd; the process will use the same UID and GID of the user.

In my docker configuration `--userns-remap=default` which means docker run as `dockremap user` and `dockremap group`. Depend of your OS, you might have to create this user.

### How to declare userns-remap ?  
- --userns-remap=default  
- --userns-remap=USER  
- --userns-remap=USER:GROUP  

ref: https://docs.docker.com/engine/security/userns-remap/  

### Which user for userns-remap ?
If the goal of isolating `docker-daemon` is to reduce the surface of threat you should choose a user which not in any special group like sudo, wheel or even docker.  

If you use docker-image which don't let you change the PUID and PGID inside the container, you might want to maps the `GROUP` to the `users group` (--userns-remap=:USER:`users`).

The avoid more complexity, be sure your user running the Docker-daemon have a lower UID than the users group, such as in my example I create `dockremap` with the `id 500` and adding the users group which have the `id 1000`.  

---

# Let's start
I'm assuming you're Docker-daemon runas `dockremap` and this user have `UID=500`  
`adduser dockremap -SDHu 500 -g users -s /sbin/nologin`  

And your mapping is into subuid and subgid files
`echo dockremap:500:65536 | tee -a /etc/subuid /etc/subgid`  

So when you `ls -l /var/lib/docker/`  you have a directory representing your ( USERid .GROUPid ) or something like `500.500` or `500.1000`.  

Than you're docker daemon run in a userspace and your ready to lunch your container.

> PS: Please run all script or command with as a user and not as root; which means this user (it could be admin, core, rescue, docker,...) have to have access to the docker-daemon which is accessible via the group docker.  Yes at this point it's look useless because the group docker is like the wheel/sudo group, but who knows, someday they will change this and you will already have this good habit.

Again because I want to work with a concret example I will use the core user.

So as core user, which have (id:1000) and his in the users group (id:1000)

[ToBeContinue]
