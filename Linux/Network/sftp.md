sftp - secure file transfer protocol

**If we added public key to target machine, we can now use it also for sftp**

`$ sftp brian@(ip address)` use that on machine, which has private key.

`$ put (locally made file)` for copying from local machine to remote machine. 

pwd will show you only remotely working directory but **lpwd** will show local working directory.

!echo and !cat also works as local versions of remotely working echo and cat.

E.g. (changing names)
`$ put sourcefile.txt newnamefile.txt`