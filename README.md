# NetBooting MacMini over MAAS

To generate EFI file, issue following command:
```bash
grub-mkimage -v -d /usr/lib/grub/x86_64-efi/ -O x86_64-efi -p '(tftp)/boot/grub' -o ./mactel64.efi -c ./grub.cfg-mactel.efi normal configfile net efinet tftp http efi_gop efi_uga all_video gzio part_gpt ext2 echo linux linuxefi memdisk eval sfs regexp
```
Then copy **mactel64.efi** to MAAS location:
```bash
sudo cp mactel64.efi /var/lib/maas/boot-resources/current/
```
