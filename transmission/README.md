# Transmission  
A simple BitTorrent client with the ability of being remotely controlled.  

## PURPOSE
I believe you could find answers to **General Questions** <a href="../../master/README.md" title="" target="_blank">here</a>.  
Don't hesitate to <a href="https://github.com/jodumont/docker/issues/new" title="Ask a question by submitting an issue on github." target="_blank">ask any question</a> even if it's to know which colour is the blue sky ? :)  
But please before, <a href="https://github.com/jodumont/docker/issues?utf8=%E2%9C%93&q=is%3Aissue" title="Please look for a similar question through all the issues before opening a new one." target="_blank">try to see if someone had a similar question.</a>

## IMAGE MAINTAINER
Almost the most popular transmission image ;)  
- <a href="https://hub.docker.com/r/linuxserver/transmission/" title="Transmission a simple BitTorrent client with the ability of being remotely controlled." target="_blank">linuxserver/transmission</a>

### Why this image
- base on Alpine  
- no root process  
- UID and GID as variables  

## REQUIREMENT

## ENVIRONMENT VARIABLE *(.env file)*  
To access the Download and Watch directory you must define in them with a full path in your .env  
`DOWNLOADS=`  
`WATCH=`  

such as an example :  
`DOWNLOADS=/srv/downloads/torrent`  
`WATCH=/srv/downloads/watch`  

Also, be sure you give read/write access to theses directory to the user **abc** which you could control the ID via these two variables :  
`PGID=`  
`PUID=`  

### HINT
Generally I create a user **abc** on the host and add it into the group **users**.  

For the **GENERAL ENVIRONMENT VARIABLES** please refer to <a href="../ENV.md" title="GENERAL ENVIRONMENT VARIABLES" target="">GENERAL ENVIRONMENT VARIABLES</a> 
