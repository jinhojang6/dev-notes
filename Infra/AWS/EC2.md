## EC2
Amazone Elastic Compute Cloud (Amazone EC2) is a web service that provides secure, resizable compute capacity in the cloud. EC2 is based on instances that can be connected through SSH.

- [Overview](https://aws.amazon.com/ec2/?nc1=h_ls)
- [Getting-started](https://aws.amazon.com/ec2/getting-started/)
- [How to create an EC2 Instance](https://www.guru99.com/creating-amazon-ec2-instance.html)

<br/>

## Replacing a lost key pair
- https://aws.amazon.com/premiumsupport/knowledge-center/ec2-windows-replace-lost-key-pair/?nc1=h_ls

<br/>

## AWS Linux 

```
# Git
sudo yum update -y
sudo yum install git -y
git version

# Node
sudo yum install -y gcc-c++ make
curl -sL https://rpm.nodesource.com/setup_18.x | sudo -E bash -
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

# Ubuntu

## Key permission
chmod 600 ~/.ssh/id_rsa

```
# Node
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg

NODE_MAJOR=20
echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list

sudo apt-get update
sudo apt-get install nodejs -y

# Yarn
sudo npm install --global yarn

# Docker
sudo apt install docker.io

# [ERROR] Got permission denied while trying to connect to the Docker daemon socket ~
sudo usermod -aG docker $USER
newgrp docker

# Docker-compose
https://docs.docker.com/compose/install/

sudo apt install docker-compose

[old]
sudo apt install curl
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version

#root
sudo su -
enable root: https://tecadmin.net/how-to-enable-ssh-as-root-on-aws-ubuntu-instance/


enable password sign-in

sudo passwd ubuntu

sudo vi /etc/ssh/sshd_config
PasswordAuthentication yes

sudo service sshd restart
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
