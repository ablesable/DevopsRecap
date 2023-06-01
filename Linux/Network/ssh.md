- Allows to remotly execute commands on different computers.
- Underneath Git uses ssh.

For testing, I used reccomended multipass tool from Canonical. It allows to make Ubuntu virtual machines using Hyper V or Virtual Box

### Configuration of virtual machine
It's not a wsl, but completely new virtual machine 
1. Installing multipass
2. `$ multipass launch --name secondary` (makes vm named secondary)
3. Clicking on multipass icon can open new shell, and starts vm named primary.
4. `$ multipass shell secondary` for opening shell of new vm.
5. Now we have two virtual machines locally. 

### Configure ssh keys
1. On secondary, add user `$ sudo useradd -s /bin/bash -m -g ubuntu brian ` User brian, added to ubuntu group, with home folder made on default, with bash shell to use.
2. Change a password for that user.
3. Change a user by su command.
4. **Secondary will be our target machine to connect from Primary**.
5. We add ssh keygen to primary ` $ ssh-keygen -t rsa`. Private key remains on primary, but public key will be given to secondary.
6. Private Key will be stored in /.ssh/id_rsa.
7. Switch to secondary. Next make /.ssh directory and create file called authorized_keys.
8. From primary, copy public key from .ssh folder and pase it to authorized_keys.
9. Right now change permission to .ssh folder on secondary machine to only user (`$ chmod 700`).
10. Change permission to .ssh/authorized_keys on secondary machine ($ chmod 600).

To this point, I generated a ssh keys on primary (public and private), copied public key from primary to secondary, change permissions on secondary .ssh folder and authorized keys file. 

### Testing ssh connection between two virtual machines
1. get ip address from target machine `$ ifconfig`
2. inet address is fabricated virtual network address created by multipass.
3. get that inet address and use on primary machine.
4. `$ ssh brian@(inet copied address)`

**Now, we connected between two virtual machines.**