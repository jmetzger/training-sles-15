# 2020sles15
Training Potsdam SLES 15

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


## Registration ## 

### Registering on command line ###

```
# Command -r registration code (from suse.com) 
sudo SUSEConnect -r xxxxxxxxxxx -e name@domain

# Documentation 
https://documentation.suse.com/sles/15-SP2/html/SLES-all/cha-register-sle.html#sec-register-sle-system

```



## Software ##

### Modules ### 

Add functionality to your system (starting from SLES 15) 

You can find a list of modules here.

All modules are available for you installaton 

#### Managing modules with SUSEConnect 

```
sudo SUSEConnect --list-extensions
```

### Extensions ### 

They hold specific software-extension like high availability.
You have to buy a license to use them.


### Show available modules and extensions ###

```
SUSEConnect --list-extensions 
```

### Activate module "Desktop" -  so that it is possible to install Gnome ###

```
SUSEConnect -p sle-module-desktop-applications/15.2/x86_64
```


### Show available patterns ### 

```
# patterns = groups of software packages, that can be easily installed
zypper search patterns_
```

