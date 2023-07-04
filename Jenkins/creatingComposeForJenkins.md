1. Creating docker-compose file (example in the same folder as this md).
2. Image is jenkins/jenkins
3. Ports on a host will be 8080 mapped to 8080 port in the container.
4. in the same folder creating **jenkins_home** directory for mouting files from container.
5. Mapping jenkins home to /var/jenkins_home in the container.
6. Defining network (**net**).
7. Giving authority of jenkins_home, for **container can write** `sudo chown 1000:1000 jenkins_home -R` In my scenario file was made by admin so already has a lot of privilages. 
8. Running by `docker-compose up -d`
9. Running `docker logs -f jenkins` for logs **there will be first password for configuration**
10. Installing packages in the browser.

---- 
Changing dns:
1. Check ip of a localmachine by `ip a`
2. copy this ip addres to the host file in the System32 on windows.
3. Because of that we can go to the site on specific name we gave.