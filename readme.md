## Minimalistic rEFInd theme

[rEFInd](http://www.rodsbooks.com/refind/) is a simplistic boot manager for UEFI
based systems. This is a clean and minimal theme for it.

![rEFInd Minimalistic](https://dl.dropboxusercontent.com/u/762200/github/rEFInd-minimal/rEFInd-bootscreen.png)

### Usage on a Mac

To use this theme you'll want to clone it into the same directory as your rEFInd
efi executable (usually `/EFI/refind/`). Then you will want to add the line
`include minimal-theme/theme.conf` to the end of your `refind.conf`.
````
echo "include minimal-theme/theme.conf" >> refind.conf
````

To set the icons for your entries you will want to add the `icon` configuration
to each menuentry which points to the icon under `minimal-theme/icons` that you
would like to use for that entry.

Here's an example configuration (from the screenshot)

````
menuentry "OSX" {
	icon /EFI/refind/minimal-theme/icons/os_mac.png
	loader /EFI/Apple/Boot/bootmgfw.efi
}
menuentry "Arch Linux" {
	icon /EFI/refind/minimal-theme/icons/os_arch.png
	loader vmlinuz-linux
	initrd initramfs-linux.img
	options "rw root=UUID=dfb2919d-ff78-48db-a8a7-23f7542c343a loglevel=3"
}

menuentry "Windows" {
	icon /EFI/refind/minimal-theme/icons/os_win.png
	loader /EFI/Microsoft/Boot/bootmgfw.efi
}

````

Entries that are autodetected should also show the proper icons.

### Attribution
Original [rEFInd-minimal](https://github.com/EvanPurkhiser/rEFInd-minimal) theme by [@EvanPurkhiser](https://github.com/EvanPurkhiser)

The OS icons are from [Lightness for burg](http://sworiginal.deviantart.com/art/Lightness-for-burg-181461810)
by [SWOriginal](http://sworiginal.deviantart.com/).

The background image was found on [wallbase.cc](http://wallbase.cc) and doesn't seem to have any attributions.

