# LVM 

## Beispiel filesystem vergrößern 

```
lvresize --resizefs -L +128MiB /dev/vg_data/lv_data
```

## Snapshot erstellen 

```
# Erstellt ein Snapshot in der gleichen Volume Group
# muss die gleiche volume group sein 
# -s -> snapshot erstellen 
# "snapshot" is not allowed as name, as it is reserved 
lvcreate -L 2G  -s  -n mysnapshot /dev/myvg/datavolume
```

## Snapshot restore (zurückspielen) 

```
# show the data like ls in logical volume 
lvs 
```

```
# Explaining lvs 
s : for snapshot, “o” meaning origin for the original logical volume copied to the snapshot;
w : for writeable meaning that your snapshot has read and write permissions on it;
i : for “inherited”;
a : for “allocated”, meaning that actual space is dedicated to this logical volume;
o : (in the sixth field) meaning “open” stating that the logical volume is mounted;
s : snapshot target type for both logical volumes
```

```
# To restore it, you need to mount the backup 
```

## Reference 

  * https://devconnected.com/lvm-snapshots-backup-and-restore-on-linux/
