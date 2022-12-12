# Zypper commands 

## Pakete für ping und nslookup ohne Server-Module zu installieren 

```
zypper install -y bind-utils 
zypper install -y iputils 

zypper search test_
# Pakete installieren von modulen die nicht noch nicht installiert sind 
zypper search-packages 

zypper source-install apache2-mod_nss

```

```
# Programme finden, die nicht installiert sind 
zypper install command-not-found 
```
