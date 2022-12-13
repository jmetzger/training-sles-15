# Einrichten von sudoers 

## Walkthrough 

```
# Auskommentieren, damit password des Nutzers abgefragt und nicht root 
# Defaults targetpw   # ask for the password of the target user i.e. root
# Jeder, der in der Gruppe wheel ist, hat alle sudo root-Rechte 
%wheel ALL=(ALL) ALL
```
