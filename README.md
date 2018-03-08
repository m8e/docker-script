# docker
[DOK-uhr] who is involved in loading and unloading applications.

#### Tested and developped to be in production under a host using :
- grsecurity
- PAX
- cgroupfs
- userns

## WYgIWYse (What You get Is What You should expect)
- independant docker
  - official image *as possible or at least well known image*  
  - **no, no, no** docker-compose, rancher, kubernetes, ...
- run with the least privilege  
  - **--no-new-privileges**  
  - specific **cgroups** when required
  - seccomp (*planned*)  
- run / (able to run / (must be/expect to run)) the **docker daemon** with
    - \--icc=false  
    - \--userns-remap  
    - \-H unix:///var/run/docker.sock -H tcp://0.0.0.0  
- ready for swarm (*beta*)
  - use docker-volume instead of mounting point (*but possible to specify a mount point into the running file*)
