# Ubuntu autoinstall config file sample by Diolinux

This is a sample file, it can be used as reference for your own installations. 
The password is: 123

Use the URL of the file in the Ubuntu Installer (Subiquity)

## Create a custom ISO (alternative)

1. Download the oficial Ubuntu ISO.
2. Extract it to a folder of your preference
3. Put the `autoinstall.yaml` file into the root of the ubuntu's extracted folder
4. Than, use this command to create the ISO:

````bash

xorriso -as mkisofs -r -V "Name of the Image" -o ../name_of_your_custom_iso.iso -J -l -b boot/grub/i386-pc/eltorito.img -c boot.catalog -no-emul-boot -boot-load-size 4 -boot-info-table folder-with-the-ubuntus-iso-files/
````
To use the above commands make sure you have installed `xorriso` and `mkisofs` on your system.

Variables on the above command:
- `"Name of the Image"`: Is the name you want to appear on the file manager. TL;DR; is the ISO's label.
- `../name_of_your_custom_iso.iso`: Is the name and path (to be saved) for your custom ISO.
- `folder-with-the-ubuntus-iso-files/`: Path to the folder containing the files of the Ubuntu ISO that you extracted in step 2.

## Where to find the custom ISO?

You should find the custom ISO on the upper directory of your working folder, unless you change the parameter `../name_of_your_custom_iso.iso`
i.e. If you extracted the Ubuntu's ISO files on your downloads directory, the custom ISO will be in your home folder.
