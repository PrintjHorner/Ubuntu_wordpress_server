# Install software

    apt update && apt upgrade -y
    
    apt install mysql-server -y
    mysql_secure_installation
   
    add-apt-repository ppa:nginx/stable
    apt-get update
    apt-get install nginx
    
    apt install php-mysql php-fpm monit -y

      
  ### On Ubuntu 16.04: Start and enable services at start-up 
  
    systemctl start nginx php7.0-fpm monit
    systemctl enable mysql nginx php7.0-fpm monit     
    
    
  # 1 Configure mysql
  # 2 Configure Nginx
  # 3 Configure php
    
    
    
