# Docker
[DOK-uhr] who is involved in loading and unloading applications.

## Who
I'm a poor lonesome cowboy and a long way from home, wandering in the **World Wild Web** and trying to make it better.  
*Listen I'm a poor lonesome Cowboy Original Song from Lucky Luke in <a href="assets/Lucky_Luke-Im_a_poor_lonesome_cowboy.wbem" title="Lucky Luke I'm a poor lonesome Cowboy" target="_blank">wbem</a> | <a href="assets/Lucky_Luke-Im_a_poor_lonesome_cowboy.mp3" title="Lucky Luke I'm a poor lonesome Cowboy (Yes mp3 was liberated in April 2017 by Fraunhofer.)" target="_blank">mp3</a> format.*

As a Certified **Linux System Administrator** by Linux Foundation and Certified **Ethical Hacker** by EC-Council,  
I :
- Build, maintain and improve servers and services for startups, SMEs and NGO;  
- Coach teams and companies about **IT Security** and **Linux** servers and services;  
- Train organizations, kids and families on **Commons sense** and **Digital citizenship**.  
## What
I don't want to reinvent the wheel, **this is not a bunch of docker image**. Yes! I believe it's possible to find smart people/teams who build docker image well or better to use the official one.  

### You get
- **independent and versatile** : able to run standalone or with docker-gen  
  - **official image** *as possible or at least well-known images*  
- run with the **least privilege**  
  - no service running as root in the container  
  - able to run with a docker in a **user namespace**  *(--userns-remap)*  
  - **--no-new-privileges** : when it runs, it can't claim new privileges  
  - specific **capabilities** when required  
  - specific **cgroups** when required (*planned*)  
  - specific **seccomp** (*planned*)  
### You need
#### REQUIRED
 - Linux host
 - Curl
 - Dockerd*  

##### *\*[how to install docker](https://docs.docker.com/install/)*
#### RECOMMENDED
- Basic **Bash** and **Git** experience
- Text editor on the Linux host  
#### NICE TO HAVE
- DNS management knowledge  
- A domain name who's supporting dynamic change  
## When
It's could be a good start to use these scripts if you want to start fast and/or if you want to build on top of them.  If you do so, please, don't be silly and share with the community your progress, change and bugs. All comments will be considered.  
## Where
I personally run them on different **docker hosts** such as :
- Alpine Linux with grsecurity/PaX  
- Debian/Ubuntu with AppArmor
- CentOS/Fedora with SELinux  
  
on a **nodev**,**noexec**,**nosuid** partition  
with a **docker daemon** running with :  
  - no intercommunication *(--icc=false)*  
  - no new privileges  *(--no-new-privileges)*
  - user namespace *(--userns-remap=)*\*
##### *\*incompatible with SELinux.*
## Why
Too often I see **docker images** running services as root and/or **docker daemon** also running as root. Also too often I see/saw scripts, Dockerfile, docker-compose, rancher-compose, ... being complex and tight to infrastructure. By default Docker philosophy is to make services universal and easy to deploy, to take over.
## How
All scripts are meant to run alone without any further specification/configuration but this will be obviously not practical and versatile; so you may interact with any of them by creating a **.env file** at the same level of the script you want to run.

You could find more info about general environment variables [here](ENV.md).  
If a project have **specific variable** available, they will be specified inside the **README project** under the **ENVIRONMENT VARIABLE *(.env file)*** section.  
### But What happen if I don't define a .env file ?  
The container will use the docker run -P argument which will expose port randomly. *(more info about <a href="https://docs.docker.com/v1.11/engine/reference/commandline/run/" title="" target="_blank">EXPOSE</a>)*
### FEW EXAMPLES
#### SIMPLE EXAMPLE
Here portainer will be available under your : **Linux host IP** on **port 8800**  
````
CONTAINER=portainer
PORT=8800

mkdir $CONTAINER
cd $CONTAINER

curl -o run https://raw.githubusercontent.com/jodumont/docker/master/$CONTAINER/run

echo "$PORT" > .env  

/bin/bash run  
````
#### ANOTHER SIMPLE EXAMPLE
Here portainer will be available under : myportainer.mydomain.tld\*  

````
CONTAINER=portainer
VHOST=myportainer.mydomain.tld  

mkdir $CONTAINER
cd $CONTAINER

curl -o run https://raw.githubusercontent.com/jodumont/docker/master/$CONTAINER/run

echo "$VHOST" > .env  

/bin/bash run  
````
#### A LITTLE BIT MORE COMPLEX EXAMPLE
Here portainer will still available under : myportainer.mydomain.tld\* but we use a **proxy** which accepting request only from a specific **docker network**.  

````
CONTAINER=portainer

mkdir $CONTAINER
cd $CONTAINER

curl -o run https://raw.githubusercontent.com/jodumont/docker/master/$CONTAINER/run

cat > .env << EOM
VHOST=myportainer.mydomain.tld  
VNET=proxy
EOM

/bin/bash run  
````
##### *Don't forget is you don't have a DNS server pointing to the domain, you could   
1' modify /etc/hosts or C:/Windows/hosts and forge your DNS entry for you host only like this :  
````
Linux.Host.IP   myportainer.mydomain.tld  
192.168.192.1.1 myportainer.mydomain.tld  
````
2' build a local DNS server with PiHole  
### <a href="DISCLAIMER.md" title="a statement in which a person or company states that they are not directly involved with or responsible for something." target="_blank">DISCLAIMER</a>