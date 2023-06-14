## **Documentation for Project 8**

### Entire View of ec2 List 
![list-of-ec2's](./Images/entire-view-of-ec2-list.png)

### TCP Port 80 Opened
![TCP-Port80](./Images/TCP-port-80-opened-in-security-group.png)

### Apache Load Balancer Installation and Enabling Module
`sudo apt update`
`sudo apt install apache2 -y`
`sudo apt-get install libxml2-dev`


`sudo a2enmod rewrite`
`sudo a2enmod proxy`
`sudo a2enmod proxy_balancer`
`sudo a2enmod proxy_http`
`sudo a2enmod headers`
`sudo a2enmod lbmethod_bytraffic`
![Enabling-Module-and-installing-apache-loadbalancer](./Images/Apache-load-balancer-and-module-enabling.png)

### Apache status verified as running
`sudo systemctl restart apache2`
`sudo systemctl status apache2`
![Apache-up-and-running](./Images/Apache-2-up-and-running.png)

### Configuring Load Balancer
`sudo vi /etc/apache2/sites-available/000-default.conf`
![Load-Balancer-config](./Images/Load-Balancer-Config.png)

### Confirming even distribution of traffic by load Balancer

### HTTP get request logged in webserver 1 log file

`sudo tail -f /var/log/httpd/access_log`
![log-record-after-several-refresh-for-Webserver 1](./Images/several-get-request-received-from-lb-WS1.png)

### HTTP get request logged in webserver 2 log file

`sudo tail -f /var/log/httpd/access_log`
![log-record-after-several-refresh-for-Webserver 2](./Images/several-get-request-received-from-lb-WS2.png)

### Local DNS Names Resolution Configuration

`sudo vi /etc/apache2/sites-available/000-default.conf`
![updating-Lb-config-file-with-the-arbitrary-names](./Images/updating-loadbalancer-configfile-with-the-arbitrarynames.png)

### Curling our webservers for access locally by our webservers

`curl http://Web1`
`curl http://Web2`
![accessing-our-webservers-locally-from-load-balancer](./Images/result-of-curl-for-Web1.png)

![accessing-our-webservers-locally-from-load-balancer](./Images/result-of-curl-for-Web2.png)