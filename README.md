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

```
