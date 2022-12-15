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
So it is mainly used
```

## Ext4:

```
Verbesserung von ext2
Journalbasiert, abwärtskompatibel
Rocksolid 
Quicker but not so many Features for Data Integrity 
```

==== Linux Dateisysteme - Welche gibt es ? ====

  * ext2/ext3 
  * ext4
  * btrfs 
  * zfs 
  * xfs 
  * reiserfs 

==== Vergleich der wichtigsten Filesysteme ====

^  ^Ext3^Ext4^XFS^Btrfs^
|Production-Ready|  ✔|  ✔|  ✔|teilweise|
|Dateisystem Tools|	e2fsprogs (mke2fs, resize2fs , e2fsck, tune2fs)|	e2fsprogs (mke2fs, resize2fs , e2fsck, tune2fs)|	xfsprogs (mkfs.xfs, xfs_growfs, xfs_repair, xfs_admin)|	btrfs-progs (mkfs.btrfs, btrfs resize, btrfsck, btrfs filesystem)|
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

==== Der Klassiker ext2/ext3 bzw. ext4 ====


==== Das Journal-Filesystem ====

  * Alle Änderungn werden in ein Journal geschrieben, bevor sie auf Festplatte geschrieben werden 
  * Crashed das System z.B. durch Stromausfall, kann mit Hilfe des Journals wieder ein konsistenter Stand hergestellt werden. 
  * --
  * Filesysteme mit Journal 
  * --
  * ext3/ext4
  * XFS 
  * reiserfs 

==== Der Klassiker ext2/ext3 bzw. ext4 ====

  * ext2 (kein Journal) 
  * Erstes Filesystem von Linux überhaupt 
  * ext3 identisch mit ext2, jedoch mit Journaling 
  * ext4 Weiterentwicklung von ext3

==== Was ist das Standard-Dateisystem für welches Linux ? ====

^Linux Distribution^Standard-Dateisystem^
|Debian (ab Debian 7.0 Wheezy)|Ext4|
|RHEL / CentOS (ab RHEL 7.0)|XFS|
|SLES (ab SLES 12)|Btrfs für /, XFS für Datenpartitionen|
|Ubuntu (ab Ubuntu 9.04)|Ext4|

==== Vergrößern / Verkleinern von Dateisystemen ====

^          Dateisysteme und ihre Möglichkeiten        ^^^
^ Dateisystem ^  Online  ^^  Offline  ^^
^ ^ Vergrößern ^ Verkleinern ^ Vergrößern ^ Verkleinern ^
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
