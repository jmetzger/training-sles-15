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
