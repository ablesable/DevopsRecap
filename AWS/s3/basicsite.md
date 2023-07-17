In order to host basic site with a domain, the bucket name should have a part of a domain name in its name. 

Buckets are private by default. In order to be open to public, in the time of their creation uncheck "Block all public access". 

In the properties tab we have to enable **static website hosting**. There we should specify index and error html file to display from this s3 bucket. Unchecking blocking all public access is not enough. We have to specify access for public in **Permission** tab. 

In permission tab in **Bucket policy** paste example json file content available in this folder. 

Action **GetObject** will allow to get objects and content of html and image file for general audience. 