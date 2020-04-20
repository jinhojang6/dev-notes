## EC2
Amazone Elastic Compute Cloud (Amazone EC2) is a web service that provides secure, resizable compute capacity in the cloud. EC2 is based on instances that can be connected through SSH.

- [Overview](https://aws.amazon.com/ec2/?nc1=h_ls)
- [Getting-started](https://aws.amazon.com/ec2/getting-started/)
- [How to create an EC2 Instance](https://www.guru99.com/creating-amazon-ec2-instance.html)


## Replacing a lost key pair
- https://aws.amazon.com/premiumsupport/knowledge-center/ec2-windows-replace-lost-key-pair/?nc1=h_ls


## Prerequisites (AWS Linux)
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
