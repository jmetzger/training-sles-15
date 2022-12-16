# Chrony

## Server 

```
chronyc 
(daemon not running from the beginning) 
chronyd 

systemctl status chronyd 

yast ntp-client

systemctl start chronyd 
systemctl status chronyd
systemctl enable chronyd

chronyc activity
chronyc
> activity 
```

## Konfigurieren 

```
yast ntp-client 
```

## Start ntp-server

  * manual 
  * ohne daemon synchronisieren
  * now and at start 

### ohne Daemon synchronisieren 

  * synchronisierung erfolgt ohne daemon im interval (default 5 min)
  * Intervall läßt sich einstellen. 

## Konfigurationsquelle (ntp-server über) 

```
statisch.
dynamisch: erfolgt über dhcp 
```
