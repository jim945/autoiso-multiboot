# autoiso-multiboot
Multiboot config for GRUB2

Automatically searches for iso images containing /boot/grub/loopback.сfg in the /bootisos directory of all partitions and generates a boot record for them. 
There are built-in configs for some images without loopback.сfg

Installation
1. Copy the files to the $prefix of your grab or any subfolder. I have it in the autoiso folder next to grub.cfg
2. Add an item to the menu of your grub.cfg

```
submenu "autoiso" {
configfile "${config_directory}"/autoiso/autoiso.cfg
}
```

3. Copy the LiveCD images to the /bootisos directory of any partition
4. Reboot
