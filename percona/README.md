# Percona
Percona Server is a fork of the MySQL relational database management system created by Percona.

## PURPOSE
I believe you could find answers to **General Questions** <a href="../../master/README.md" title="" target="_blank">here</a>.  
Don't hesitate to <a href="https://github.com/jodumont/docker/issues/new" title="Ask a question by submitting an issue on github." target="_blank">ask any question</a> even if it's to know which colour is the blue sky ? :)  
But please before, <a href="https://github.com/jodumont/docker/issues?utf8=%E2%9C%93&q=is%3Aissue" title="Please look for a similar question through all the issues before opening a new one." target="_blank">try to see if someone had a similar question.</a>

## IMAGE MAINTAINER
The official build by percona  
- <a href="https://hub.docker.com/_/percona/" title="Percona Server is a fork of the MySQL relational database management system created by Percona." target="_blank">percona</a>

## ENVIRONMENT VARIABLE *(.env file)*
For the **GENERAL ENVIRONMENT VARIABLES** please refer to <a href="../ENV.md" title="GENERAL ENVIRONMENT VARIABLES" target="">GENERAL ENVIRONMENT VARIABLES</a>  

### EXTRA
If **no PASSWORD** is define, on the first run the script will define a 24 caracters password and store it into a read-only file named `./.secret`  
However; you could define PASSWORD inside `./.env` too.

If **no NETWORK** is specified; on the first run the script will create a network named `db_percona` and this container will receive the static IP `172.33.6.254`.  
**NOTICE :** All docker-scripts will discover the appropriate network and connect on if they require it.
