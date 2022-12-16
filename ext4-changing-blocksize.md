# Changing the block size 

```
# To change block size of ext4, partition needs to be unmounted 
umount /mnt/platte 
blockdev --getbsz /dev/sdb1 

# not possible 
blockdev --setbsz 8192 /dev/sdb1 

# you can try 
mkfs.ext4 -b 8192 /dev/sdb1 
## answer
## 8192 to big for ext4 (4096) max 
## proceed anyway 
```




## Ref:

  * https://ext4.wiki.kernel.org/index.php/Ext4_Disk_Layout#:~:text=With%20the%20default%20block%20size,disk%20in%20little%2Dendian%20order.
  * Blocksizes up to 64KiB are possible (see Dokument)
