# Änderrungen von SLES 12 zu SLES 15 

## Modul - Struktur 

  * Unified Installer 
  * SLES 15 ist dann in Module aufgespalten 
  * Jedes Modul hat einen klar definitierten Bereich mit verschiedenen Lebenszyklen und Update Zeitplänen 

## zypper search-packages 

  * Durchsucht auch repos die noch nicht eingebunden sind 
  * z.B. zypper search-packages iperf 
    * findet paket in package hub 

## Kernel/Bash Versionen 

  * Kernel 4.4 -> 4.12
  * Bash 4.3.42 -> 4.4.23

## ntp -> chrony 

  * NTP -> chrony 

## Firewall 

  * SuSEFirewall2 -> firewalld 

## Python 

  * python2 -> python3 

## SMT (Subscription Management Tool) -> RMT (Registry Mirror Tool und Registration Proxy für SCC (SuSE Connect Center)

  * Spiegeln von SUSE Repositories und Kunden Repositories. Proxy zu anderen RMT Servern

## LDAP 

  * OpenLDAP -> 389ds (LDAPv3 compliant server) 

## Automation 

  * puppet->salt
  * salt wird für das Konfigurationsmanagement benutzt. SUSE Manager 

## X-Server 

  * X11 -> Wayland 
  * Gnome is now using Wayland by default (X11 before) 

## unrar -> unar 

  * Unar ersetzt aus lizenzrechtlichen Gründen unrar.

## Changes in /etc/systemd/system.conf 

```
#CtrlAltDelBurstAction=reboot-force
#DefaultStartLimitIntervalSec=10s
#DefaultIOAccounting=no
#DefaultTasksMax=15%
```

## /etc/init.d 

  * is now empty
  * SystemV Skripte können nicht aktiviert werden
  * Falls nötig paket insserv-compat nachinstallieren

## Netzwerk 

  


## SuSE-release 

  * Datei SuSE-release ist entfernt worden

## Floppy-Disk 

  * Floppy Disk Support ist entfernt worden

## Filesysteme 
  
  * ReiserFS - Support ist entfernt worden
  * Der Installer blockiert eine Migration, wenn 
    * ReiserFS entdeckt wird

## Finger 
 
  * Den Befehl gibt es nicht mehr 

## cronjobs 

```
Einige cronjobs unter /etc/cron 
(hourly,daily,weekly,monthly) sind jetzt als Timer Units implementiert worden.
snapper-timeline.tiner
backup-sysconfig.timer 
backup-rpmdb.timer
check-battery.timer 
snapper-cleanup.timer
systemd-tmpfiles-clean.timer 
btrfs-balance.timer 
fstrim.timer 
#btrfs
```

```
