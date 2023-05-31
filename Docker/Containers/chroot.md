## Features
- chroot, namespace and control group. This three things are consist to form a Container.
- How to make that two processes doesn't see each other? `chroot` command. It just do another root/new system based on a previous layer (operating system).

## Running container
- `$ sudo docker run -it --name docker-host --rm --privileged ubuntu:bionic`
- It runs ubuntu:bionic operating system inside of a container. 

## chroot running from container
- chroot . bash (this will not work)
- basicaly chroot is telling the system that from this directory (.) we're making new root/system and then we are going to run bash.
- But bash is not available, because right now we don't have big features from our basic operating system. 
- We're copying bash `cp bin/bash my-new-root/bin/` but it still not gonna work, cause we don't have importan libraries that running bash depends on.
- To check libraries that e.g. bash depends on: `# ldd bin/bash`
- We should copying libraries to new directories lib and lib64 by pasting paths from `# ldd bin/bash`
- After that we can run chroot and then bash in new dictionary.
- Do the same steps (copying feature/program to new root and then important libraries).
- Now, besides that we just are in the directory called /my-new-root, this is like a root directory to new system/changed root. `pwd` command will show `\` after running bash.
  