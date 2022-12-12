# Verzeichnisaufbau 

## /etc 

  * Verzeichnis für Konfigurationsdatein 

## /dev 

  * Devices (Alle Gerätedateien - Ein- und Ausgabegeräte, wie bspw. Festplatten, Mouse) 

## /mnt 

  * früher viel verwendet: 
  * für händisches Einhängen gedacht (per Hand mounten) 
 
## /media 

  * das neue / moderne (wird heutzutage meistens verwendet) 
  * Verzeichnis für automatisch eingehängte Devices (z.B. usb-stick)

## /opt 

  * Große Softwarepaket (z.B. LibreOffice, OpenOffice, Dritt-Anbieter) 

## /boot 
 
  * Files for booting (e.g. kernel, grub.cfg, initital ramdisk)

## /proc 

  + Schnittstelle zwischen Kernel und User-Space (für Programme, Benutzer)
  + Kommunikation erfolgt über Dateien 

## /root 
  
  * Heimatverzeichnis des root-Benutzers 

## /run 

  * Dateien mit Prozess-ID für laufenden Services
  * um diese gut beenden zu können 

## /tmp 

  * Temporäre Dateien 
  * Löschen von Dateien kann unter /etc/tmpfiles.d verwaltet werden (erfolgt von systemd auf Tagesbasis) 

## /sys 

  * wie proc 
  * Schnittstelle zwischen Kernel und User-space 

## /var (=variable daten) 

  * Hier liegen Daten, die sich häufig ändern
  * Log-Dateien, Datenbanken, Spool-Dateien, Cache-Dateien 

## /lib 

  * Bibliotheken (.so, .ko) wie unter Windows *dll's 

## /sbin

  * Programme zur Systemadministration 

## /bin 

  * Normale Programme für alle (executables) 
