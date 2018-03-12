# Portainer
A Simple management UI for Docker.
## PURPOSE
I believe you could find answers to **General Questions** <a href="../../README.md" title="" target="_blank">here</a>.  
Don't hesitate to <a href="https://github.com/jodumont/docker/issues/new" title="Ask a question by submitting an issue on github." target="_blank">ask any question</a> even if it's to know which colour is the blue sky ? :)  
But please before, <a href="https://github.com/jodumont/docker/issues?utf8=%E2%9C%93&q=is%3Aissue" title="Please look for a similar question through all the issues before opening a new one." target="_blank">try to see if someone had a similar question.</a>

## IMAGE MAINTAINER
The official build by portainer  
- <a href="https://hub.docker.com/r/portainer/portainer/" title="Portainer a Simple management UI for Docker." target="_blank">portainer/portainer</a>

## REQUIREMENT
Portainer need to interact with your docker daemon. To make this happen you have two choices :  
~~1' Running the container with root privilege.~~

2' Exposing your Docker Socket via TCP*  

I beleive the second method is the better because, anyway if you want to manage a bunch Docker Host with via one Docker Manager you will have to expose it.

##### *\*<a href="https://docs.docker.com/engine/reference/commandline/dockerd/" title="Search for '-H ' inside the Docker Daemon Documentation." target="_blank">Docker Daemon Documentation</a>*

## ENVIRONMENT VARIABLE *(.env file)*
For the **GENERAL ENVIRONMENT VARIABLES** please refer to <a href="../ENV.md" title="GENERAL ENVIRONMENT VARIABLES" target="">GENERAL ENVIRONMENT VARIABLES</a>  