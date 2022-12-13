# Einrichten von sudoers 

## Walkthrough 

```
# Auskommentieren, damit password des Nutzers abgefragt und nicht root 
# Defaults targetpw   # ask for the password of the target user i.e. root

# Attention: Comment out, because otherwice everybody is allowed to do anything 
# ALL   ALL=(ALL) ALL   # WARNING! Only use this together with 'Defaults targetpw'!


# Jeder, der in der Gruppe wheel ist, hat alle sudo root-Rechte 
%wheel ALL=(ALL) ALL
```

## Spezifische Rechte für Benutzer 

```
groupadd externer 
useradd -m -aG externer extern
passwd extern 
```

```
#vi /etc/sudoers.d/externer 
%externer ALL=(ALL) /usr/bin/systemctl restart *,/usr/bin/chown
```

```
chmod 440 /etc/sudoers.d/externer 
```

```
# Testen 
su - extern 
sudo systemctl restart sshd 
```
