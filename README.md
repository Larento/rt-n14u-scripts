# rt-n14u-scripts
Assortment of scripts I made to easily install Entware and/or other cool stuff on ASUS RT-N14U. Router is running stock ASUS firmware `3.0.0.4.380_8285`. These scripts allow me to:
- version control my router configs using git;
- control my local network `hosts` file on the router remotely;
- update scripts to a new version over-the-air by sending UDP packets.

# Installation
1. Prepare USB drive with ext2/ext3.
2. Clone this repo to USB drive.
3. Connect USB to router.
4. Connect to router using telnet.
5. Check for USB volumes with `blkid`. In my case it was `/dev/sda1`.
6. Mount USB volume to `/tmp/opt`.
7. Run `install` script from cloned folder.

Scripts will be installed on `JFFS` partition, `/jffs/homebrew`. Installer sets up a startup script. It relies on the `script_usbmount` feature, so the `startup` script will only run if the correct USB drive is inserted. As usual you can install Entware packages with `opkg install`. This makes it easy to use the stock firmware with official drivers, while allowing for useful, but previously unavailable modifications like `netcat`, `git`, `dropbear`, `transmission` and so on.

I think this is a good and safe alternative for those, who don't need much use out of this particular router. You are probably asking yourself right now, couldn't you just install a custom firmware and be done with it? Yes, I could've. But I was too lazy to disconnect all of the router's setup to flash the firmware. After all, laziness is the mother of invention.
