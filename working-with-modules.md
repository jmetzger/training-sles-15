# Working with moudules/extensions 

## General 

  * modules extend functionality
  * extensions also, but require an additional license (registration key)
  
## Modules 

Add functionality to your system (starting from SLES 15) 

All modules are available for you installaton 

## list modules/extensions with SUSEConnect 

```
sudo SUSEConnect --list-extensions
```

## Extensions ### 

They hold specific software-extension like high availability.
You have to buy a license to use them.

### Activate module "Desktop" -  so that it is possible to install Gnome ###

```
SUSEConnect -p sle-module-desktop-applications/15.2/x86_64
```
 
## Documentation

  * Basics about extensions: https://documentation.suse.com/sles/15-SP1/html/SLES-all/art-modules.html
