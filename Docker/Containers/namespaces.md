Processes are still seen even after changed roots. ps command used in old root and ps command in the new root env still show us the same results. 
That's why we need namespaces. For limiting container environments.

- After running long process like tail -f secret.txt in my-new-root directory. I can go to another shell in the same container. The main command is:
- `$ docker exec -it docker-host bash`
- running ps aux will show me tail proccess
- From there I can use `$ kill (number)` and another shell process will not be working. 

So our main goal is to limit that power!
- after apt-get update for updating our container's ubuntu use `$ apt-get install debootstrap -y` for important tools. 
- ` # debootstrap --variant=minbase bionic /better-root` is going to install minimal version of debootstrap (minbase) for bionic ubuntu inside /better-root folder.
- <b>Debustrap is a Debian bootstrap</b> so this command will make a  Debian minimum bare file system based on a bionic ubuntu.
- `# chroot . bash` inside /better-root directory now will make new root <b> flawlessly </b>.

## After creating new root with debian file system:
- Right now we have the same situation with processes, network and so on like before. 
- `# unshare --mount --uts --ipc --net --pid -fork --user --map-root-user chroot /better-root bash` Will make... a <b>wall</b> shortly speaking between two environments.
- This is essentialy <b> Unsharing namespaces </b>

## Showing different processes in new root env:
- after unsharing inside new root env we cannot use `ps aux` command.
- Fot that, we have to mount:

`mount -t proc none /proc` \
`mount -t tmpfs none /tmp` \
`mount -t sysfs none /sys` 

In old root we can see some processes of new root env, but from parents perspective is a normal. From child perspective we cannot see anything from old root.