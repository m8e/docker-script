# Tiny Tiny RSS  
A feed reader allows you to access your RSS/atom feeds from everywhere, through the web or mobile apps.

## PURPOSE
I believe you could find answers to **General Questions** <a href="../../master/README.md" title="" target="_blank">here</a>.  
Don't hesitate to <a href="https://github.com/jodumont/docker/issues/new" title="Ask a question by submitting an issue on github." target="_blank">ask any question</a> even if it's to know which colour is the blue sky ? :)  
But please before, <a href="https://github.com/jodumont/docker/issues?utf8=%E2%9C%93&q=is%3Aissue" title="Please look for a similar question through all the issues before opening a new one." target="_blank">try to see if someone had a similar question.</a>

## IMAGE MAINTAINER
Almost the most popular Tiny Tiny RSS image ;)  
- <a href="https://hub.docker.com/r/linuxserver/tt-rss/" title="Tiny Tiny RSS a feed reader allows you to access your RSS/atom feeds from everywhere, through the web or mobile apps." target="_blank">linuxserver/tt-rss</a>

### Why this image
- base on Alpine  
- no root process  
- UID and GID as variables  

## REQUIREMENT
This container requires a PostgreSQL or MySQL database instance.

## ENVIRONMENT VARIABLE *(.env file)*  
The script will seek you could use postgres or mysql/maria/percona with this container. You simply have to define which one in you .env file, such as :  
`DB=postgres`  
Then the script will connect to db_$DB network. Obviously you have to prepare the database and the dbuser.  

Also, like on every LinuxServer image you could change the ID for the user **abc** by these two variables :  
`PGID=`  
`PUID=`  

For the **GENERAL ENVIRONMENT VARIABLES** please refer to <a href="../ENV.md" title="GENERAL ENVIRONMENT VARIABLES" target="">GENERAL ENVIRONMENT VARIABLES</a> 
