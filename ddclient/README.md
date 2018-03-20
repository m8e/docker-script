# DDClient
A client used to update dynamic DNS entries for accounts on Dynamic DNS Network Service Provider such as :  
- ChangeIP  
- CloudFlare  
- dnspark  
- dslreports  
- DtDNS  
- dyndns  
- EasyDNS  
- Google Domains
- Hammernode  
- Loopia  
- NameCheap  
- OrgDNS  
- ZoneEdit  

## PURPOSE
I believe you could find answers to **General Questions** <a href="../../README.md" title="" target="_blank">here</a>.  
Don't hesitate to <a href="https://github.com/jodumont/docker/issues/new" title="Ask a question by submitting an issue on github." target="_blank">ask any question</a> even if it's to know which colour is the blue sky ? :)  
But please before, <a href="https://github.com/jodumont/docker/issues?utf8=%E2%9C%93&q=is%3Aissue" title="Please look for a similar question through all the issues before opening a new one." target="_blank">try to see if someone had a similar question.</a>

## IMAGE MAINTAINER
The most popular DDClient container by LinuxServer Teams.
- <a href="https://hub.docker.com/r/linuxserver/ddclient/" title="DDClient a client used to update dynamic DNS entries for accounts on Dynamic DNS Network Service Provider." target="_blank">linuxserver/ddclient</a>

### Why this image
- base on Alpine  
- no root process  
- UID and GID as variables  

## REQUIREMENT
You have to edit/configure the :/config/ddclient.conf file by hand than start or restart the container.  

It's possible to edit the file by running this command :  
`docker exec -ti ddclient vi /config/ddclient.conf`

A better solution will be provide in a near future.  

## ENVIRONMENT VARIABLE *(.env file)*  

For the **GENERAL ENVIRONMENT VARIABLES** please refer to <a href="../ENV.md" title="GENERAL ENVIRONMENT VARIABLES" target="">GENERAL ENVIRONMENT VARIABLES</a> 