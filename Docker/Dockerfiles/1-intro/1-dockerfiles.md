dockerfile file in this directory is an big instruction for docker to build a container.

Running dockerfile was easy when vs code is running in wsl. In package directory on Linux section of this repo, there are instructions how to install that.
But because our host has docker desktop, building this is easy also on windows.
`$ docker build .` build dockerfile which is in the current folder.
`$ docker run (id form logs)` runs what was specified in a `CMD`.  
`$ docker build --tag my-container` building with tagging a name instead of the id.