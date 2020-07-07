## EC2
Amazone Elastic Compute Cloud (Amazone EC2) is a web service that provides secure, resizable compute capacity in the cloud. EC2 is based on instances that can be connected through SSH.

- [Overview](https://aws.amazon.com/ec2/?nc1=h_ls)
- [Getting-started](https://aws.amazon.com/ec2/getting-started/)
- [How to create an EC2 Instance](https://www.guru99.com/creating-amazon-ec2-instance.html)

<br/>

## Replacing a lost key pair
- https://aws.amazon.com/premiumsupport/knowledge-center/ec2-windows-replace-lost-key-pair/?nc1=h_ls

<br/>

## Prerequisites 
AWS Linux
```
# Git
sudo yum update -y
sudo yum install git -y
git version

# Node
sudo yum install -y gcc-c++ make
curl -sL https://rpm.nodesource.com/setup_12.x | sudo -E bash -
sudo yum install -y nodejs
node -v
npm -v

# Yarn
sudo npm install yarn -g
yarn -v

# Python
sudo yum install python3
python3 --version
```

Ubuntu
```
# Node
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash
sudo apt-get install -y nodejs

# Yarn
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update && sudo apt install yarn
(ref: https://classic.yarnpkg.com/en/docs/install/#debian-stable)

# Docker
sudo apt-get remove docker docker-engine docker.io
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker
docker --version

# Docker-compose
- sudo apt install curl
- sudo curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version

# [ERROR] Got permission denied while trying to connect to the Docker daemon socket ~
sudo usermod -aG docker $USER
newgrp docker

#root
sudo su -
enable root: https://tecadmin.net/how-to-enable-ssh-as-root-on-aws-ubuntu-instance/
```

<br/>

## Extending volume

- [Resizing a volume](https://hackernoon.com/tutorial-how-to-extend-aws-ebs-volumes-with-no-downtime-ec7d9e82426e)

- [Extending a Linux file system after resizing a volume](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html)

```
df -h
-------------------------------------------------
Filesystem       Size  Used Avail Use% Mounted on
/dev/xvda1       8.0G  1.9G  6.2G  24% /
/dev/xvdf1       8.0G   45M  8.0G   1% /data
-------------------------------------------------

sudo growpart /dev/xvda 1

Verify:
lsblk
```

<br/>

## Changing instance type
- https://www.cloudsqueeze.ai/how-to-change-an-aws-ec2-instance-type-a-step-by-step-guide/index.html
