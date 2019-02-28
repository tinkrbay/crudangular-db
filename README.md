sudo su

yum install -y httpd mariadb-server git

systemctl start mariadb

chkconfig mariadb on

mysql -u root


>>> Within the mysql prompt:

create user php@'%' identified by 'php'

create database cellar

grant all privileges on cellar.* to php@'%';

exit

You should be in /home/ec2-user/

mysql -u root -p cellar  < /home/ec2-user/wine-cellar-php-sql-dump/cellar.sql
