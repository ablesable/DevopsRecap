The steps I did for wsl ubuntu:

- First install kubectl [link](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
- this will be in /usr/local/bin/kubectl
- `kubectl cluster-info` will show error, cause we don't have a cluster.
- install minikube [link](https://minikube.sigs.k8s.io/docs/start/)
- minikube, also will be in /usr/local/bin
- `minikube start` for starting a cluster
- Then we can create our pod from yaml.

local cluster created!

-----
1. Create pod from yaml here in directory.
2. Create Replication controller from yaml in directory.

Pod and replica controller with additional pods created!
