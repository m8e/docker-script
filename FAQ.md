# FAQ
A list of questions and answers relating to a particular subject, especially one giving basic information for users of a website.

## What
This FAQ intent to answer question for the project docker-scripts. Because docker-scripts invent nothing new, most of `What is this` or `What is that` must be ask to your favorite search engine or wikipedia.  

## About Database engine (mysql, mariadb, postgres and percona)  
### Why I could only run one instance ?
Most of Database engine recommand to dedicate at minimum of 512MB of RAM and to be confortable most engine will require to dedicate 2 to 4Gb. So now with this aspect in mind, do you wan to run one database instance per service as most docker-compose do ?

#### This is not a new concept
Before the containarization era, a database engine was use for more than one application. Also, reputable docker project, like Cloudron, concentrate all database on a unique engine. In fact, it facilitate the backup and the maintenance.

### Why creating a network for each database engine ?
By creating a network we restrain who could access to theses database. Also the network is create as an <a href="https://docs.docker.com/engine/reference/commandline/network_create/#network-internal-mode" title="" target="_blank">internal network</a> without gateway which means it's virtualy impossible to communicate with the rest of the World.

````
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
172.54.32.0     *               255.255.255.0   U     0      0        0 br-db_postgres
````
