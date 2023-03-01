# autoiso-multiboot https://archlinux.org.ru/forum/topic/19029/
Multiboot config for GRUB2

Automatically searches for iso images containing /boot/grub/loopback.сfg in the $iso_dirs directory 
of all partitions and generates a boot record for them. (mark "loopback" in menu)
There are built-in configs for some iso images without loopback.сfg 
in "loopback" directory (mark "autoiso" in menu)
User configs in "user_cfg" directory (mark "user_cfg" in menu)

Installation
1. Copy the files to the $prefix of your grab or any subfolder. I have it in the autoiso folder next to grub.cfg
2. Add an item to the menu of your grub.cfg

```
submenu "AutoISO - load Linux from .iso " {
	set iso_dirs="/ /bootisos /iso"
	export iso_dirs
	configfile "${prefix}"/autoiso/autoiso.cfg
}
```
3. Change iso_dirs="/ /bootisos /iso"
4. Copy the LiveCD images to the $iso_dirs directory of any partition
5. Reboot

Spaces in image names are not supported!!!
