**CRI** - Container Runtime Interface 
**OCI** - Open Container Initiative: **imagespec** & **runtimespec**

Imagespec is a specification how image should be build.
Runtimespec is a specficication how runtime of a container should be working.

Docker wasn't support CRI, so **dockershim** was developed.

**Container d** in the end was compatible with CRI. The Container d is a **container runtime**.
Dockershim was not supported anymore from 1.24 version, and a container d starts to be autonomonous runtime. **It's now a seperate project**.

-----
**ctr** is a cli tool for container d. Not really user friendly besides of debugging.
**nerdctl** tool is more user friendly and made as docker like cli. 

**crictl**- used to debug container runtimes compatible with CRI. From Kubernetes community.



![Photo](https://imgur.com/eV2BUGm)