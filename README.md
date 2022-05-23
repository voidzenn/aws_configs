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
  
