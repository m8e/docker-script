# GENERIC ENVIRONMENT VARIABLE *(.env file)*
Depending on your setup, you may want to pass these variables.  

## CONTAINER NAME
By default it will be the name of the directory where the **run script** is been stocked.  
To replace this behavior, define the variable **CONTAINER** with **YOUR_CONTAINER_NAME** and put this line inside a .env  
`CONTAINER=YOUR_CONTAINER_NAME`

## DATA STORAGE
By default a docker-volume will be create and named with **$CONTAINER** variable.  
1. If you want your data locally inside **./data**, copy the next line into your .env  
`DATA="$( cd "$(dirname "$0")" ; pwd -P )"/data`  

2. You could also specify any local directory by replacing **/my/directory** with a non-relative and complete path  
`DATA=/my/directory`

## MEMORY LIMIT
It define a hard limits on memory available for containers.  
If you want to overwrite the default policy, replace **%%M** in this example and put the line inside your .env  
Don't forget the **M** for Megs or **G** for Gigs.  
`MEMORY=%%M`  

## NETWORK
$NETWORK is definitly a critical variable, it will determine how you access the container.  

If you run the container without any option, as I call in standalone mode, Docker will binds each exposed port to a random port on the host.  

But if you want to specify on which port you will access your container define the variable PORT in your .env file, such as in this example the container will be available on port **8800** :  
`PORT=8800`  

### With proxy and docker-gen
You probably eared about the famous https://github.com/jwilder/docker-gen title="" target="_blank">docker-gen</a> by Jason Wilder which detect new container and generate configuration file for services like haproxy, nginx, fluentd or logrotation. Than if you use it with nginx or haproxy you're lucky because you could interact with it via variables.  

To reach the container via a domain or a subdomain you just have to declare it via the $VHOST in your .env file which will give something like this : 
`VHOST=mycontainer.mydomain.ltd`  

Docker-gen also use the EXPOSE parameter to generate the file configuration; but what happening if many ports are exposed ?  
Usually Docker-gen will bind the port 80 or if this one is not declare, it will be the first port exposed. To be sure the run script will 

### or works with docker-gen
[[ -n $VHOST ]] && \
  NETWORK="-e VIRTUAL_HOST=$VHOST"
[[ -n $VHOST && $VPORT ]] && \
  NETWORK="-e VIRTUAL_HOST=$VHOST -e VIRTUAL_PORT=$VPORT"
[[ -n $VHOST && $VNET ]] && \
  NETWORK="-e VIRTUAL_HOST=$VHOST --network=$VNET"
[[ -n $VHOST && $VPORT && VNET ]] && \
  NETWORK="-e VIRTUAL_HOST=$VHOST -e VIRTUAL_PORT=$VPORT --network=$VNET"


## RESTART POLICY
By default the restart policy is **on-failure:5**.  
If you want to overwrite my restart policy, replace **YOURPOLICY** in this example and put the line inside your .env  
`RESTART=YOURPOLICY`  

Visit [restart policies](https://docs.docker.com/engine/reference/run/#restart-policies-restart) for more information about it.  

### <a href="DISCLAIMER.md" title="a statement in which a person or company states that they are not directly involved with or responsible for something." target="_blank">DISCLAIMER</a>
At this point no variable have validation; if you pass a wrong option, it may result from a simply non-working container to losing or corrupting your data or your host or worst an ali3n invasion.

- *For the corruption part, I personally don't know how this could happen but who knows.*
- *For the alien invasion I'm still doing research about it.*