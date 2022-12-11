# SUSEConnect

## Register SLES with email and license key  

```
# Command -r registration code (from suse.com) 
sudo SUSEConnect -r xxxxxxxxxxx -e name@domain
```

## Unregister SLES with email and license key 

```
# unregister/deregister system / otherwice, you cannot reuse the key 
sudo SUSEConnect -d -e name@domain
```
