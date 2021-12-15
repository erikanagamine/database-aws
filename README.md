# Database on AWS

Some studies about database in AWS


User data:
```
#!/bin/bash
sudo yum update -y
sudo yum install libXft -y
mkdir /tmp/hammerdb
cd /tmp/hammerdb
wget https://github.com/TPC-Council/HammerDB/releases/download/v4.3/HammerDB-4.3-Linux.tar.gz > download.log
tar -zxvf HammerDB-4.3.tar.gz > install.log

#systems manager
sudo yum install -y https://s3.region.amazonaws.com/amazon-ssm-region/latest/linux_amd64/amazon-ssm-agent.rpm
sudo systemctl status amazon-ssm-agent

sudo systemctl enable amazon-ssm-agent
sudo systemctl start amazon-ssm-agent
sudo systemctl status amazon-ssm-agent

#web
yum update -y amazon-linux-extras install -y lamp-mariadb10.2-php7.2 php7.2
yum install -y httpd mariadb-server
systemctl start httpd
systemctl enable httpd
usermod -a -G apache ec2-user
chown -R ec2-user:apache /var/www
chmod 2775 /var/www
find /var/www -type d -exec chmod 2775 {} \;
find /var/www -type f -exec chmod 0664 {} \;
echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php


```
