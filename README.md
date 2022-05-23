### EC2 installations

#### install httpd
  - sudo yum update -y
  - sudo amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2 (dont include lamp-mariadb10.2-php7.2 if you only want php)
  - sudo yum install -y httpd
  - sudo systemctl start httpd
  - sudo systemctl enable httpd

#### install codedeploy-agent
  - sudo yum update
  - sudo yum install ruby
  - sudo yum install wget
  - #!/bin/bash
    CODEDEPLOY_BIN="/opt/codedeploy-agent/bin/codedeploy-agent"
    $CODEDEPLOY_BIN stop
    yum erase codedeploy-agent -y
  - cd /home/ec2-user
  - wget https://aws-codedeploy-us-east-2.s3.us-east-2.amazonaws.com/latest/install  
  - chmod +x ./install
  - sudo ./install auto
  - sudo service codedeploy-agent status
  - sudo service codedeploy-agent start

#### install composer

  - sudo curl -sS https://getcomposer.org/installer | sudo php
  - sudo mv composer.phar /usr/local/bin/composer
  - sudo ln -s /usr/local/bin/composer /usr/bin/composer
  - sudo composer install  

#### install mysql
  - sudo yum install https://dev.mysql.com/get/mysql80-community-release-el7-5.noarch.rpm
  - ls /etc/yum.repos.d ( optional )
  - sudo yum repolist ( optional )
  - sudo amazon-linux-extras install epel -y
  - sudo yum -y install mysql-community-server
  - sudo systemctl enable --now mysqld
  - systemctl status mysqld ( optional )

---------------------------------------------------------------------------------------------------------
### Solutions and Tips

#### httpd.conf location
  - /etc/httpd/conf/httpd.conf
  
#### fix permission error
  - chmod -R 777 <folder-name>
