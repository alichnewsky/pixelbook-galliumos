# Setup for my Pixelbook

## Developer mode.
`Esc + Reload + Poweroff` (LEFT SIDE button on the edge)

`Ctrl-D` when in the scary red ! screen shows up.

Then wait for 2 beeps

Followed by "Preparing for Developer Mode" This may take a while, Do not turn your computer off until it has restarted screen

Then, you can boot an USB stick. (eventually installing an OS from said USB stick)

## Crouton from within ChromeOS
1. Developer mode ON
1. OS Verifcation is OFF screen
1. get to chrome os. reconfigure. need to know your wifi password to do this
1. `Ctrl-Alt-T` : crosh shell in browser
 ```
 shell
 sudo -i
 crossystem dev_boot_usb=1 dev_boot_legacy=1
 poweroff
 ```
## Now attempt to boot live USB key
Usb key contains :
```
md5 -r galliumos-skylake-2.1.iso
a79ae9e2e58aa86903605c5677a384c4 galliumos-skylake-2.1.iso
```
1. insert your usb disk. boot the machine
1. type `Ctrl-L`
1. Get the BIOS and a boot menu
1. Select option 1. to boot from USB
1. Select option 1. to boot and start graphical interface for Gallium OS : HANG
 OR
1. Select option 2. to boot in pseudo terminal? in low runlevel? Get 2 or 3 kernel stacktraces, boot hung

Plenty of pictures of boot logs and stack traces.

## Attempt #1 (boot with GUI : "Gallium OS Live Image and Installer)
blue screen with Gallium OS logo. With icon spinning, until it hangs

## Attempt #2 (GalliumOS Console (single user, text mode))
Did not really think to capture pictures or movie after 10 seconds into the boot, when things started going wrong
![](boot2-console/image1.JPG?raw=true)
![](boot2-console/image2.JPG?raw=true)
![](boot2-console/image3.JPG?raw=true)
![](boot2-console/image4.JPG?raw=true)
![](boot2-console/image5.JPG?raw=true)
## Attempt #3 (Live Image and Installer)
blue screen, followed by black screen and power down very quickly. Nothing to show.

## Attempt #4 (Console)
different kernel stack trace. hung.

THis time I recorded a very shaky movie that eventually lead to more screenshots.

The stack traces seem different...
![](boot4-console/image_1.png?raw=true)
![](boot4-console/image_2.png?raw=true)
![](boot4-console/image_3.png?raw=true)
![](boot4-console/image_4.png?raw=true)
![](boot4-console/image_5.png?raw=true)
![](boot4-console/image_6.png?raw=true)
![](boot4-console/image_7.png?raw=true)
![](boot4-console/image_8.png?raw=true)
And that's where it hangs until I removed the USB drive (got sign of life) and gave up.