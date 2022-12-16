# Mariadb

## Walktrough 

```
zypper install -y mariadb 
systemctl start mariadb 
systemctl enable mariadb
```
## Daten, wo ? 

```
# Erst nach dem ersten Start unter 
# /var/lib/mysql 
#
```

## Grundabsichern 

```
mysql_secure_installation 
```

## Einige Kommandos 

```
mysql>
show databases;
use mysql;
select * from user;
select * from user \G
pager less 
select * from user \G
nopager 
```

## MariaDB nach aussen öffnen 

```
# vi /etc/my.cnf.d/z_settings.cnf 
[mysqld]
listen-address=0.0.0.0
```

```
systemctl restart mariadb
firewall-cmd --add-service mysql 
firewall-cmd --add-service mysql --permanent 

echo "CREATE USER ext1@'%' identified by 'password'" | mysql
echo "GRANT ALL ON *.* TO ext1@'%'" | mysql
```

## MariaDB Client 

```
mysql -u ext1 -p -h <ip-des-mariadb-servers>
mysql -u ext1 -p -h 10.163.24.108 
```
