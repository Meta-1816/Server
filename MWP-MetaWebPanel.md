# Server Configuration For Web Panel
yum update


# Install LAMP [Linux,Apache,MySql,Php]
https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-centos-7


# 1. install Apache Web Server
yum install httpd

systemctl start httpd

systemctl enable httpd


# 2. install Marya DB
yum install mariadb-server mariadb

systemctl start mariadb

sudo mysql_secure_installation

systemctl enable mariadb.service


# 3. install Php MySql
yum install php php-mysql

systemctl restart httpd


# 4. Install PhpMyAdmin


# 5. Install FtpServer

