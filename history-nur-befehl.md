# History nur Befehl 

```
# -s ' ' ersetzt alle doppelten leerzeichen durch eines
# cut -d -> setzt das Trennzeichen fest
# -f5- zeigt die Spalte 5 und alle weiteren Spalten an 
history | tr -s ' ' | cut -d ' ' -f5-
```
