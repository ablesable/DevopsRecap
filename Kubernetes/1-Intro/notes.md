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

-----

 If we are making cluster from scratch, we have to install, configure **etcd** as a service in our master node.    

`--advertise-client-urls (ip-of-a-server:2379)` this is the place with an address where etcd service listens. 

When we use **kubeadm**, this tool deploys etcd server as a **pod** in a **kube system namespace**.

-------
**Kube-api** server is the only component, which interacts with etcd data store.
Making a new node in a cluster:
1. Making a request for a new node to the kubeapi server. 
2. Authenticating a user.
3. Validating the request.
4. Retrieving data.
5. Updating ETCD.
6. Info goes to Scheduler and a Kublet.

