# Adminer
A Simple database management.  
- *ElasticSearch*  
- *Firebird*  
- *MS-SQL*  
- **MySQL/MariaDB/Percona**  
- Oracle  
- **Postgres**  
- SimpleDB  
- SQLite 2/3  
- **MongoDB**  

## PURPOSE
I believe you could find answers to **General Questions** <a href="../../README.md" title="" target="_blank">here</a>.  
Don't hesitate to <a href="https://github.com/jodumont/docker/issues/new" title="Ask a question by submitting an issue on github." target="_blank">ask any question</a> even if it's to know which colour is the blue sky ? :)  
But please before, <a href="https://github.com/jodumont/docker/issues?utf8=%E2%9C%93&q=is%3Aissue" title="Please look for a similar question through all the issues before opening a new one." target="_blank">try to see if someone had a similar question.</a>
## IMAGE MAINTAINER
The official build by adminer  
- <a href="https://hub.docker.com/_/adminer/" title="Adminer a simple database management." target="_blank">adminer</a>
## REQUIREMENT
Your database container must be launch and available before you start Adminer.  

## ENVIRONMENT VARIABLE *(.env file)*  
This container meant to be use with containers like postgres and percona. The scripts will look for network starting by db_ and will be connected to them.  

For the **GENERAL ENVIRONMENT VARIABLES** please refer to <a href="../ENV.md" title="GENERAL ENVIRONMENT VARIABLES" target="">GENERAL ENVIRONMENT VARIABLES</a> 