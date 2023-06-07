# C Groups
- Thanks to them we can control how much cpu, memory and so on, some containers have.
- One container can get 100 percent of physical memory (or pseudo physical memory - VM situation). This dangerous in shared servers. To prevent that scenario from happening, we use cgroups. 
- For cgroups tool `# apt-get install -y cgroup-tools htop`
- htop is a tool to see how much memory and cpu is used in environment.

## Creating new cgroup

- `# cgcreate -g cpu,memory,blkio,devices,freezer:/sandbox`
- After creating a cgroup, we should unshare our specific environemt for namespaces. Then  use specific cgroup on that unshered environment, but assigning that to a cgroup **must be from other host** - you cannot limit yourself.
- From another terminal, we now search bash process in that unshared, cut container, then we use `# cgclassify -g cpu,memory,blkio,devices,freezer:sandbox (number of that another container/new root/other environemt process)`
- In the same terminal typing `# cat /sys/fs/cgroup/cpu/sandbox/tasks` will show us what process was added to that group.
- `# cat /sys/fs/cgroup/cpu/sandbox/cpu.shares` showing priorities.
- Everything what is in the tree - please use only 5% of available power `# cgset -r cpu.cfs_period_=100000 -r cpu.cfs_quota_us=$[ 5000 * $(getconf _NPROCESSORS_ONLN) ] sandbox`
- Everything what is in the tree - please use only 80Mb of memory, anything more will be runs out of memory.
- After setting - this is for stats `# cgget -r memory.stat sandbox`