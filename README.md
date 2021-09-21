## Minimalistic Black rEFInd theme

[rEFInd](http://www.rodsbooks.com/refind/) is an easy to use boot manager for UEFI
based systems. This is a clean and minimal black theme for it.

![rEFInd Minimalistic Black](screenshot.png)

### Usage

1.  Locate your refind EFI directory. This is commonly `/boot/EFI/refind`
    though it will depend on where you mount your ESP and where rEFInd is
    installed. `fdisk -l` and `mount` may help.

2.  Create a folder called `themes` inside it, if it doesn't already exist

3.  Clone this repository into the `themes` directory.

4.  To enable the theme add `include themes/rEFInd-minimal-black/theme.conf` at the end of
    `refind.conf`.

Here's an example menuentry configuration (from the screenshot)

```nginx
menuentry "Arch Linux" {
	icon /EFI/refind/themes/rEFInd-minimal-black/icons/os_arch.png
	loader vmlinuz-linux
	initrd initramfs-linux.img
	options "rw root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows" {
	icon /EFI/refind/themes/rEFInd-minimal-black/icons/os_win.png
	loader /EFI/Microsoft/Boot/bootmgfw.efi
}

menuentry "OSX" {
	icon /EFI/refind/themes/rEFInd-minimal-black/icons/os_mac.png
	loader /EFI/Apple/Boot/bootmgfw.efi
}
```

Entries that are autodetected should also show the proper icons.

### Attribution

Based on [rEFInd-minimal](https://github.com/EvanPurkhiser/rEFInd-minimal) by Evan Purkhiser.

Most icons are taken from the original [rEFInd-minimal-black](https://github.com/andersfischernielsen/rEFInd-minimal-black) by Anders Fischer-Nielsen.
