# Install software

    apt update && apt upgrade -y
    
    apt install mysql-server -y
    mysql_secure_installation
   
    add-apt-repository ppa:nginx/stable
    apt-get update
    apt-get install nginx
   
    apt install php-mysql php-fpm monit -y
    apt install php-json php-xmlrpc php-curl php-gd php-xml php-mbstring -y
      
  ### On Ubuntu 16.04: Start and enable services at start-up 
  
    systemctl start nginx php7.0-fpm monit
    systemctl enable mysql nginx php7.0-fpm monit     
    
    
# 1 Configure mysql
# 2 Configure Nginx
open port
                       
    sudo ufw allow 'Nginx HTTP'
 Create a system user for site
    
    adduser yourusername
    mkdir -p /home/yourusername/logs
   
 Modify config  
    
    nano /etc/nginx/conf.d/yoursitename.conf

    
  # 3 Configure php
    
    cp /etc/php/7.0/fpm/php.ini /etc/php/7.0/fpm/php.ini.ORIG
    sed -i "s/;cgi.fix_pathinfo=1/cgi.fix_pathinfo=0/" /etc/php/7.0/fpm/php.ini
    systemctl restart php7.0-fpm
    
  # 4 Test by creating php info page
    
    sudo nano /var/www/html/info.php

``` 
<?php   
phpinfo();
``` 

    sudo rm /var/www/html/info.php
    
    
