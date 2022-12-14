# Training SuSE Linux Enterprise 15 (SLES 15) 

## Agenda 

  1. Grundlagen 
     * [Änderungen von SLES 12 -> 15](changes-sles-12-15.md)

  1. Installation / Administration
     * [Working with modules/extensions](working-with-modules.md)  
     * [Working with SUSEConnect](suseconnect.md) 
     * [Systemctl](systemctl.md)
     * [firewalld](firewall/firewalld.md)
  
  1. Management with zypper and rpm
     * [Zypper commands](zypper-commands.md)
     * [Zypper cheatsheet](https://en.opensuse.org/images/3/30/Zypper-cheat-sheet-2.pdf)
     * [Find out installed packages with version](rpm-zypper-package-versions.md)

  1. Verzeichnisse und Dateitypen 
     * [Verzeichnisaufbau](verzeichnisaufbau.md)
     * [Dateitypen](dateitypen.md) 

  1. sudo 
     * [sudo unter SLES sicher einrichten](sudo-sles-15-einrichten.md)

  1. vim 
     * [vim](vim.md)
     
  1. timers 
     * [create a simple time](create-timer.md) 
  
  1. Unix-Tools 
     


## Backlog 

### Working with .ssh/config to predefine certain settings when connection

```
localhost:~/.ssh # cat config 
Host peterson2
    HostName 192.168.1.101
    User training

localhost:~/.ssh # ls -la
total 8
drwx------ 1 root root  34 Aug  5 10:14 .
drwx------ 1 root root 182 Aug  5 10:14 ..
-rw------- 1 root root  58 Aug  5 10:14 config
-rw-r--r-- 1 root root 181 Aug  5 10:14 known_hosts
```

### Networking search order for hosts 

```
localhost:/etc # grep -r "files dns" .
./nsswitch.conf:hosts:  	files dns
./nsswitch.conf:networks:	files dns
localhost:/etc # 
```

### Search for pattern recursively in folder 

```
localhost:/etc # grep -r 192.168.1.100 .
```

### Ping fehlt ?

zypper install iputils 

```
### bei installierten Paketen herausfinden, welches paket befehl bereitsstellt
zypper se --provides ping 
```

### Samba - Server ##

Gute Einführung
https://www.thomas-krenn.com/de/wiki/Samba-Server_Grundlagen

Spezialwissen (WINS-Server, Local Master Browser):
http://www.linux-praxis.de/linux3/samba6.html

SLES 15:
https://documentation.suse.com/sles/15-SP2/html/SLES-all/cha-samba.html

```
Manage samba-password db:
# list all files 
pdbedit -L 

## Important 
smbpasswd -a training # add linux user to samba password db 
``` 

```
# test configuration 
testparm 
```

### Testing connection with smbclient 

```
smbclient -U training -L //10.10.2.106
```


### The things with the acls ###

Supports windows acls 
https://wiki.samba.org/index.php/Setting_up_a_Share_Using_Windows_ACLs

But a bit tricky 

### Mount other share on other server (samba) ###

```
mount.cifs //10.10.2.106/dokumente /mnt/dokumente -o username=training,password=training
# or mount -t cifs 
```

## basic networking ##

https://documentation.suse.com/sles/15-SP2/html/SLES-all/cha-network.html#sec-network-addresses

## sed ##

Good introduction 

https://www.digitalocean.com/community/tutorials/the-basics-of-using-the-sed-stream-editor-to-manipulate-text-in-linux

```
# Recognize Email 
sed 's/.*/ &/;s/.* \([^ @]*@[^ @]*.com\).*/CENSORED/' emailstobecensored
# Ref: https://www.unix.com/shell-programming-and-scripting/181361-sed-regex-extract-email-address.html
```

### Example for awk script (splitting fields with "-" as seperator between fields) 

```
### file awktest.sh
### chmod u+x awktest.sh

#!/usr/bin/awk -f  
/tcp/ {
ORS="";
for (i=1; i<=5; i++) {
   if ( i == 1 ) print $i;
   else {
     print " - ",$i
   }
}
print "\n"
}

### Executing of script 
./awktest.sh /etc/services 
```

### Great ressources for setting specific VAR for NEWLINE and FIELDSOUTPUT-Seperator

https://www.funtoo.org/Awk_by_Example,_Part_2

## awk ## 

https://www.tutorialspoint.com/awk/awk_basic_examples.htm


## GIT pdf 

http://schulung.t3isp.de/documents/pdfs/git/git-training.pdf


## Change console layout 

```
# switch to german layout
sudo loadkeys de 
```
## grep - show header 

```
ps xo pid,comm | head -n 1; ps xo pid,comm | grep 11
```

## systemctl cheatsheet ##

https://www.linuxtrainingacademy.com/systemd-cheat-sheet/

## zypper ##
https://en.opensuse.org/images/1/17/Zypper-cheat-sheet-1.pdf

```
zypper patch-check 
# show only the first column -> result -> amount of patches that can be done 
zypper patch-check | tail -n 1 | cut -d ' ' -f1 # show field 1 -> -f1 && use space as delimiter -d ' '  
```

## autoyast ##
https://documentation.suse.com/sles/15-SP1/html/SLES-all/book-autoyast.html


## Kernel Parameters at boot time ##

https://documentation.suse.com/sles/15-SP1/html/SLES-all/cha-boot-parameters.html

## Kernel - crashkernel ## 

https://www.suse.com/de-de/support/kb/doc/?id=000016171


## Package Management ## 

Cheatsheet: https://danilodellaquila.com/en/blog/linux-package-management-cheatsheet


## Commands ## 

```
# Kernelversion die geladen ist, anzeigen 
less filename # pager 
cat /boot/meinfile | less  # verlassen mit q + return 
uname -a 
# which - zeigt alle Vorkommen eines Befehls im Pfad -> echo $PATH
which depmod 
# show all line with c at the beginning of line 
ls -la /dev | grep ^c
# show all lines with k at the end of the line 
ls -la /dev | grep k$ 
```





