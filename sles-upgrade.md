# SLES Upgrade 

## Schritt 1:

  * https://documentation.suse.com/sles/15-SP4/single-html/SLES-upgrade/index.html#cha-upgrade-offline

## Preparation 

### Substep 1:

* https://www.suse.com/releasenotes/index.html
* Matrix mit Links zu den Release Notes
* Release Notes studieren (Wichtige Pakete und Paketquellen durchführen)
  * https://documentation.suse.com/package-lists/sle/15-SP4/package-changes_SLE-15-SP3-GA_SLE-15-SP4-GA.txt
  * https://documentation.suse.com/package-lists/sle/15-SP4/module-changes_SLE-15-SP3-GA_SLE-15-SP4-GA.txt

### Substep 2:

  
 * Sichern von /etc,/var, /home (Empfehlung von SUSE)
 * Sicherung installierte Pakete und Paketquellen durchführen

```
zypper lr -e repositories.bak
rpm -qa --queryformat '%{NAME}\n' > installed-software.bak
```

```
# wiederherstellen
zypper ar repositories.bak.repo
zypper install $(cat installed-software.bak)
```

## Optional: media_upgrade 

```
To force the installer to only install packages from the DVD and not from network sources, add the boot option media_upgrade=1.
```
