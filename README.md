# Cent OS 7 and 8 Setup

1. Download git and nano (easy GNU nano text editor )

   `sudo yum install git -y`

   `sudo yum install nano -y`

2. Download firewallcmd `sudo dnf install firewalld` and run this command

   `sudo systemctl enable firewalld`

   `sudo systemctl start firewalld`

3. Get pub key using `ssh-keygen` and register your pub key associated with your account

4. Install docker reference [Docker Cent OS](https://docs.docker.com/engine/install/centos/).

5. Install node

   `sudo dnf module list nodejs`

   `dnf module enable nodejs:$latest`

   `sudo dnf install nodejs`

6. Install mongodb

   `nano /etc/yum.repos.d/mongodb.repo`

    Add this to /etc/yum.repos.d/mongodb.repo

   `[mongodb-org-4.4]
   name=MongoDB Repository
   baseurl=https://repo.mongodb.org/yum/redhat/7Server/mongodb-org/4.4/x86_64/
   gpgcheck=1
   enabled=1
   gpgkey=https://www.mongodb.org/static/pgp/server-4.4.asc`

   `yum -y install mongodb-org`

    Create user and change security auth /etc/mongod.conf then restart `sudo systemctl restart mongod`
    ("if failed change the ownership of the `/var/lib/mongod` and everything works

7. Install nginx

   `sudo dnf install nginx`

   `sudo systemctl enable nginx`

   `sudo systemctl start nginx`


8. Install certbot for HTTPS/SSL

   `sudo dnf install epel-release`

   `sudo dnf install certbot python3-certbot-apache mod_ssl`

   `sudo certbot —nginx -d example.com`
