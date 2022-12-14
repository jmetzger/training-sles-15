# Zypper commands 

## Pakete für ping und nslookup ohne Server-Module zu installieren 

```
zypper install -y bind-utils 
zypper install -y iputils 

zypper search test_
# Pakete installieren von modulen die nicht noch nicht installiert sind
# Cool: findet auch Pakete, wenn sie im community repo sind  
zypper search-packages iperf
zypper source-install apache2-mod_nss

```

```
# Programme finden, die nicht installiert sind 
zypper install command-not-found 
cnf iperf 
```

```
# installierte Pakete mit Version anzeigen 
zypper search --only-installed -s 
```

```
# Nach Paketen mit wildcard suchen 
zypper search yast*
zypper search yast-
```


## Show available patterns ### 

```
# patterns = groups of software packages, that can be easily installed
zypper search patterns_
```

```
