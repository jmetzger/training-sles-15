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

