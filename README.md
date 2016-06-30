# Installing FOG Server
FOG will run on a variety of Linux disros, however Ubuntu is 

## Installing Ubuntu

### Create a bootable USB with unetbootin

Download unetbootin from https://unetbootin.github.io/.

Download Ubuntu 16.04 Server from http://releases.ubuntu.com/16.04/ubuntu-16.04-server-amd64.iso.torrent. This is a torrent link, so be sure to have Transmission, qBitTorrent or similar installed.

Ensure that the target USB drive is FAT formatted prior to writing the image with unetbootin.

Open unetbootin and select the "Diskimage" radio button, then select the ISO file we downloaded. Set "Type" to "USB Drive" and "Drive" to the whatever USB drive you have selected to use.

### Install Ubuntu

Follow the install instructions for Ubuntu Server, most of the defaults are fine. 

### Partitioning
When you reach the "Partition Disks" screen select Manual then select the primary Hard Drive from the following menu, agree to create a new partition table.

#### SWAP
 - Select FREE SPACE
 - Create a new partition
 - Set the size of this partition to twice that of size of the RAM installed on the system
 - Set type to Primary.
 - Set Location to Beginning
 - Set "Use as" to "swap area", then continue to "Done setting up the partition."

#### Root 
 - Select FREE SPACE again
 - This time set the size to "max"
 - Set type to Primary.
 - Set "Use as:" to "Ext4 [...]"
 - Optionally set a disk label
 - Turn the bootable flag on, then continue to "Done setting up the partition."

Finally "Finish partitioning and write changes to disk", and accept. Ubuntu will now continue to install the base system, so feel free to grab a cup of coffee and kick back.

When prompted to configure automatic updates, select "No automatic updates."

### Software Selection
Ubuntu Server has a variety of optional software installs. We'll try to keep it lightweight, for now, install standard system utilities, and OpenSSH Server, we'll install Ubuntu desktop after the installation. Continue.

### Bootloader
Install GRUB on the MBR of your primary hard drive.

Shortly after the installation will complete, and you can now remove the USB drive and boot the system.