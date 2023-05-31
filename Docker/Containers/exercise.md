## After setting new root how to use cat?
`# echo "secret recipe" >> /my-new-root/secret.txt`
`# cp /bin/cat /my-new-root/bin`
`# ldd /bin/cat` \ 
(now I know what libraries to copy)
e.g copying one of them:
`# cpp lib/x86_64-linux-gnu/libc.so.6 /my-new-root/lib` \
After copying everything:
