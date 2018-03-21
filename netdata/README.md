# Netdata
Monitors your server with thoughts of performance and memory usage, providing detailed insight into very recent server metrics.  

## PURPOSE
I believe you could find answers to **General Questions** <a href="../../master/README.md" title="" target="_blank">here</a>.  
Don't hesitate to <a href="https://github.com/jodumont/docker/issues/new" title="Ask a question by submitting an issue on github." target="_blank">ask any question</a> even if it's to know which colour is the blue sky ? :)  
But please before, <a href="https://github.com/jodumont/docker/issues?utf8=%E2%9C%93&q=is%3Aissue" title="Please look for a similar question through all the issues before opening a new one." target="_blank">try to see if someone had a similar question.</a>

## IMAGE MAINTAINER
The official build by Netdata  
- <a href="https://hub.docker.com/r/titpetric/netdata/" title="Netdata, directly from Tit Petric." target="_blank">titpetric/netdata</a>

## REQUIREMENT
With good reason, this container need to read /proc and /sys of your host. It also requires the capacities of using PTrace.  For theses reason this container doesn't run at the userspace level.  

Don't worry; your host must run dockerd with --userns, you have nothing to do, the script manage these requirements.  

## ENVIRONMENT VARIABLE *(.env file)*  
For the **GENERAL ENVIRONMENT VARIABLES** please refer to <a href="../ENV.md" title="GENERAL ENVIRONMENT VARIABLES" target="">GENERAL ENVIRONMENT VARIABLES</a> 

### EXTRA
- <a href="https://github.com/firehol/netdata/wiki/Running-behind-nginx" title="Running behind nginx" target="_blank">Reverse Proxy</a>
