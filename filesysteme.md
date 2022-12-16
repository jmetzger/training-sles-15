# Filesysteme 

## Btrfs:

```
Bigger files are possible
snapshots 
subvolumes
Raid
more methods to achieve Data Intergrity
Special Tools needed (btrfs Tools)
df does not reflect size properly 
Mounting Snapshots
Safer because of COW (copy on Write)
-> Disabled on SLES 15 
```

## XFS 

```
Good for bigger files (Performance)
Bad Performance on small files
So it is mainly used for databases 
Schneller Filesystem check
```

## Ext4:

```
Verbesserung von ext3
Journalbasiert, abwärtskompatibel
Rocksolid 
Quicker but not so many Features for Data Integrity 
```

## Linux Dateisysteme - Welche gibt es ? 

  * ext2/ext3 
  * ext4
  * btrfs 
  * zfs 
  * xfs 
  * reiserfs 

## Vergleich der wichtigsten Filesysteme 

| | Ext3 | Ext4 | XFS | Btrfs |
| --- | ------ | ---- | --- | ----- | 
|Production-Ready|  ✔|  ✔|  ✔|teilweise|
|Max. Dateisystem-Größe|	16 TiB|	1 EiB|	16 EiB|	16 EiB|
|Max. Datei-Größe|	2 TiB|	1 EiB|	8 EiB	8 EiB|
|Online vergrößern|  ✔|   ✔|  ✔|  ✔|
|Online verkleinern|  -|  -|  -|  ✔|
|Offline vergrößern|  ✔|  ✔|  -|  -|
|Offline verkleinern|  ✔|  ✔| -|  -|
|Discard (ATA Trim)|  ✔|  ✔|  ✔|  ✔|
|Metadaten CRC|  ✔|  ✔|  ✔|  ✔|
|Daten CRC|  -|  -|  -|  ✔|
|Snapshots/Clones/Internal RAID/Compression|  -|  -|  -|  ✔|


## Das Journal-Filesystem 

  * Alle Änderungn werden in ein Journal geschrieben, bevor sie auf Festplatte geschrieben werden 
  * Crashed das System z.B. durch Stromausfall, kann mit Hilfe des Journals wieder ein konsistenter Stand hergestellt werden. 
  * --
  * Filesysteme mit Journal 
  * --
  * ext3/ext4
  * XFS 
  * reiserfs 

## Der Klassiker ext2/ext3 bzw. ext4 

  * ext2 (kein Journal) 
  * Erstes Filesystem von Linux überhaupt 
  * ext3 identisch mit ext2, jedoch mit Journaling 
  * ext4 Weiterentwicklung von ext3

##  Vergrößern / Verkleinern von Dateisystemen

### Dateisysteme und ihre Möglichkeiten 

| Dateisystem | Online | Online | Offline | Offline |
| ---  | --- |  --- | --- | --- |
|  | *Vergrößern* | *Verkleinern* | *Vergrößern* | *Verkleinern* |
| ext2/ext3/ext4 |  ja|  nein|  ja|  ja|
| ReiserFS |  nein|  nein|  ja|  ja|
| JFS |  ja|  nein|  nein|  nein|
| XFS |	 ja|  nein|  nein|  nein|
| NTFS |  nein|  nein|  ja|  ja|
| FAT |  nein|  nein|  ja|  ja|

* Vergrößern ext3/ext4 seit Kernel 2.6.

==== Vorgehen beim Verkleinern / Vergrößern ====

  * Vor dem Verkleinern einer Partition bzw. eines Logical Volume immer zuerst das Dateisystem verkleinern
  * Vor dem Vergrößern des Dateisystems immer zuerst das Logical Volume bzw. die Partition vergrößern

==== Verkleinern/Vergrößern - gute Referenz ====

  * https://wiki.ubuntuusers.de/Dateisystemgr%C3%B6%C3%9Fe_%C3%A4ndern/
