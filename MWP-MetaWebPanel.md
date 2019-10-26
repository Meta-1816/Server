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
yum install epel-release

yum install phpmyadmin

cp /etc/httpd/conf.d/phpMyAdmin.conf /etc/httpd/conf.d/phpMyAdmin.conf.backup

vi /etc/httpd/conf.d/phpMyAdmin.conf

` 
<Directory /usr/share/phpMyAdmin/>
   AddDefaultCharset UTF-8

   <IfModule mod_authz_core.c>
     # Apache 2.4
     <RequireAny>
      # Require ip 127.0.0.1
      # Require ip ::1
        Require all granted
     </RequireAny>
   </IfModule>
   <IfModule !mod_authz_core.c>
     # Apache 2.2
     Order Deny,Allow
     Deny from All
     Allow from 127.0.0.1
     Allow from ::1
   </IfModule>
</Directory>
`


# 5. Install FtpServer

