I used Microsoft Azure to build and host my own “cyber-blog” web application. I secured it with a SSL certificate, and applied Azure’s security features to protect it. 

Our Requirements Included:
- Hosting the web application using Azure’s Cloud Services
- Using Azure’s App Service resource to create the web application
Choosing a domain with “godaddy or Azure” (choose what you selected)
Deploying a Docker container which had a framework for a blog webpage
SSHing  into the container to customize the webpage
Creating a Self-signed certificate with OpenSSL 
Storing the certificate in Azure’s Key vault
Binding the certificate to the website (If you didn't select the free option)
After determining the security issues with a self-signed certificate, creating and bound a managed CA approved certificate to the web application
Deploying Azure’s Front Door, and configuring a WAF rule to restrict traffic from certain countries
Analyzing the Azure’s Security Center recommendations and applying the recommend fix

Advantages of Using Azure App Servicess:
Using Azure App Service, we can pass responsibility of managing features outside of the web application to the cloud service provider
In other words, we are only responsible for deploying and managing their web application and it's associated data
Deploying web applications can be done much faster, as user's don't have to be concerned about configuring their OS
The user doesn't have to worry about the OS and middleware maintenance, such as installing software updates and patching
Azure App services are cheaper to run than Virtual machines
Azure App services have built in features for securing and hosting a web application, such as DNS, Web App Firewalls, Domain purchasing, SSL certification binding.

Issues with Self Signed Certificate:
A Self-signed certificate is a certificate that has not been signed by a certificate authority. While these certificates are simple to create, and have no expense almost all browsers will alert the user visiting the webpage that is signed with a self-signed certificate that the webpage is not trusted by a Certificate Authority in the browser’s root store and to proceed with caution. 

Self Signed Certificate Resolution:
I created and bound a managed certificate provided by Azure, as this is a trusted certificate which has been approved by a CA which most browsers trust.

Azure Front Door and WAF feature:
Azure’s Front Door is a  Cloud Resource, it resides in front of my web application to protect it. It works on the Application Layer of the OSI Model (Layer 7). Its primary solution is a load balancer. It can incorporate a Web Application Firewall (WAF) to protect against web vulnerabilities attacks.  With the WAF, I applied a custom rule to protect against web requests from countries that I wasn't expecting any traffic from.  This could help protect against potential attacks where I knew I wasn't expecting any visitors.

Azure Security Feature and Applying Features:
Azure’s Front Door is a  Cloud Resource, it resides in front of my web application to protect it. It works on the Application Layer of the OSI Model (Layer 7). Its primary solution is a load balancer. It can incorporate a Web Application Firewall (WAF) to protect against web vulnerabilities attacks.  With the WAF, I applied a custom rule to protect against web requests from countries that I wasn't expecting any traffic from.  This could help protect against potential attacks where I knew I wasn't expecting any visitors.

