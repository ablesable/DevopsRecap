curl works really similar to wget. The address of that file from wget example will work with curl as well. **We are allowed to rename the file right now.**

`$ curl https://raw.githubusercontent.com/btholt/bash2048/master/bash2048.sh > game.sh ` (this will be download as game.sh file)

### Hitting the endpoint

1. Start API server on vm. \
`$ python3 -m http.server 8000 --bind 0.0.0.0`
2. Check in `$ ifconfig` the address of that machine. Now we can see that local server in the browser with 8000 port.
3. To get the same page but in html format type: \
`$ curl http://(ipAddress):8000`

`$ curl http://(ipAddress):8000 > somefile.txt` curl allows us to save it to files. \
`$ curl - o  otherfile.txt http://(ipAddress):8000` the same but without piping. \
e.g. \
4. `$ curl -X POST http://ipaddress:8000` This is for POST request. 
5. `$ curl -d "this is a post body" http://ipaddress:8000` it does not need POST keyword, because post requests have bodies. 


Curl also has "cookie jar" for getting all cookies into one single file.

Getting normal site:
`$ curl google.com` \
Getting normal site with redirections:
`$ curl - L google.com`


