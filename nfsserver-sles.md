# NFS-Server unter SLES einrichten 

## Server 

### Step 1: Server installieren 

```
zypper install nfsserver
```


### Step 3: Firewall einrichten 

```
firewall-cmd --permanent --add-service=nfs
firewall-cmd --permanent --add-service=mountd
firewall-cmd --permanent --add-service=rpc-bind
firewall-cmd --reload
```
