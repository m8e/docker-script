# Rainloop
Rainloop is a simple, modern & fast web-based email client with PGP support.  

## PURPOSE
I believe you could find answers to **General Questions** <a href="../../README.md" title="" target="_blank">here</a>.  
Don't hesitate to <a href="https://github.com/jodumont/docker/issues/new" title="Ask a question by submitting an issue on github." target="_blank">ask any question</a> even if it's to know which colour is the blue sky ? :)  
But please before, <a href="https://github.com/jodumont/docker/issues?utf8=%E2%9C%93&q=is%3Aissue" title="Please look for a similar question through all the issues before opening a new one." target="_blank">try to see if someone had a similar question.</a>

## IMAGE MAINTAINER
The most popular Rainloop image  
- <a href="https://hub.docker.com/r/hardware/rainloop/" title="Rainloop simple, modern & fast web-based email client with PGP support." target="_blank">hardware/rainloop</a>  

### Why this image
- base on Alpine  
- no root process  
- support postgres and mysql  
- nginx with php7  
- UID and GID as variables  

## REQUIREMENT

## ENVIRONMENT VARIABLE *(.env file)*  
Not a requirement but a nice to have, the script will seek you could use postgres or mysql/maria/percona with this container. You simply have to define which one in you .env file, such as :  
`DB=postgres`  
Then the script will connect to db_$DB network. Obviously you have to prepare the database and the dbuser.  

For the **GENERAL ENVIRONMENT VARIABLES** please refer to <a href="../ENV.md" title="GENERAL ENVIRONMENT VARIABLES" target="">GENERAL ENVIRONMENT VARIABLES</a>
