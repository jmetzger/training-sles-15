# Wicked 

## Dienste

### Netzwerk-Client starten 

```
systemctl status network 
# oder 
systemctl status wicked 
```

## Wicked-Daemon 

```
systemctl status wickedd.service 
```

## Welche Dienste gibt es ? 

```
systemctl list-units -t service | grep wicked
```


## Journal abrufen 

```
journalctl -u wicked.service 
```

## wicked - commands 

```
wicked show all 
wicked show lo 

wicked show-xml all
```
