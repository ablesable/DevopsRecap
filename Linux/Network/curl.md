curl works really similar to wget. The address of that file from wget example will work with curl as well. **We are allowed to rename the file right now.**

`$ curl https://raw.githubusercontent.com/btholt/bash2048/master/bash2048.sh > game.sh ` (this will be download as game.sh file)

### Hitting the endpoint

1. Start API server on vm. \
`$ python3 -m http.server 8000 --bind 0.0.0.0`
2. Check in `$ ifconfig` the address of that machine. Now we can see that local server in the browser.
3. 

