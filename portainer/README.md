## PURPOSE
These docker run are meant to run with a specific environment  
Such as an example and well tested with :
- [HAProxy](https://github.com/jodumont/haproxy) as proxy  
- Docker-daemon options :  
  --icc=false  
  --no-new-privileges  
  --userns-remap=default*  
  --H unix:///var/run/docker.sock  
  --H tcp://0.0.0.0*  

*theses options have intentionnaly wrong values.

## HOW TO USE
````
mkdir portainer  
cd portainer
curl -o run https://raw.githubusercontent.com/jodumont/docker/master/portainer/run  
/bin/bash run  
````
**Please pay attention at the ENVIRONMENT VARIABLE SECTION**

### IMAGE
The official build by portainer  
- portainer/portainer

## ENVIRONMENT VARIABLE
- Optionnal but highly recommanded you could pass these variables.  
- It could run as it is without any variables define by you.  

But if you want, you could define further mentionned variable by putting them into a **.env file**  

### CONTAINER NAME
By default it will be the name of the directory where it been stocked.  
To define it, replace **CONTAINERNAME** and put this line inside a .env  
`CONTAINER=CONTAINERNAME`

### DATA
By default it will create and use a volume named with $CONTAINER variable.  

1. Alternatively you could copy the next line into your .env file which will result to store your data under **./data**  
`DATA="$( cd "$(dirname "$0")" ; pwd -P )"`  

2. You could also specify a directory by replacing **/my/directory** with your complete path  
`DATA=/my/directory`

### MEMORY LIMIT
By default MEMORY LIMIT is at 64M  
It Ssecify a hard limits on memory available for containers.  
If you want to overwrite my restart policy, replace **%%M** in this example and put the line inside your .env  
Don't forget the **M** for Megs or **G** for Gigs.  
`MEMORY=%%M`  

### RESTART POLICY
By default the restart policy is **on-failure:5** which means it will try to restart 5times on-failure.  
If you want to overwrite my restart policy, replace **YOURPOLICY** in this example and put the line inside your .env  
`RESTART=YOURPOLICY`  

Visit [restart policies](https://docs.docker.com/engine/reference/run/#restart-policies-restart) for more information about it.  
