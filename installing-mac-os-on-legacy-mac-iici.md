# Installing MacOS 7.6.1 on a Macintosh IIci

These instructions used an Apple PowerMacintosh G3 running MacOS System 9.2 to create the floppy images and the experience should be the same using most any Mac + MacOS combination which can read and write High Density floppy disks.

Purchased the Mac and the hard disk drive (HDD) had been wiped clean so got the

## Acquire the disk images

> These resources

* Network Access Disk 7.5 https://macgui.com/downloads/?file_id=20094
* MacOS 7.6 Install Floppy Disk Images https://www.macintoshrepository.org/12908-mac-os-7-6-install-floppies
* MacOS 7.6.1 Update Floppy Disk Images https://udcf.gla.ac.uk/~gwm1h/macos761/index.html

## Use Disk Copy to create floppy disks

> You will use this process multiple times to create the necessary floppy disks.

* Launch Disk Copy from Applications > Utilities
* Select **Utilities** > **Make a Floppy...** from the Disk Copy menu.
* Select the .DSK image
* Click the Open button.
* Insert floppy when prompted.
* Click Yes to the 'Are you sure you want to erase "{floppy disc name}" and replace its contents with "{image disc name}?"'

## Make the target hard disk drive bootable

> You will need 1 high density floppy disk to accomplish this task.

1. Make a bootable Network Access Disk 7.5.
1. Place into the Macintosh IIci and boot.
1. Upon boot the pared down operating system may need to initialize the hard disk drive to mount. Follow the on screen prompts to perform.
1. Copy the System folder from the Network Access Disk 7.5 floppy to the hard drive.
1. When complete select Special > Restart from the MacOS menu bar.
  1. The floppy disk should automatically eject from the drive.
1. The Mac should restart to Network Access from the hard disk drive.
  1. This is a very limited operating system which allows the floppy disk drive to work for the purposes of installing the operating system.

## Create the MacOS 7.6 floppy disks

> You will need 21 floppy disks to accomplish this task.  
> 1 disk for the 'Installl Me First' disk.
> 19 disks for the operating system.
> 1 disk for the Installer Utilities.

1. Leveraging the **Use Disk Copy to create floppy disks** instructions above create a floppy disk from each `.dsk` file for MacOS System 7.6.
