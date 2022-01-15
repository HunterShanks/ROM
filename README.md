# ROM

General instructions on how to flash a custom ROM on to your Android device. These steps include GAPPS installation.

Some additional commands:
```console
$ adb start-server
$ adb kill-server
$ adb sideload something.zip
$ adb reboot [OPTION]
```
[OPTION] can be recovery, bootloader, etc


## Pre-reqs:

- Backup all of your data, we will be wiping the entire partition
- ADB + Platform tools installed (fastboot)
- Have ALL necessary files (ie recov img + zip, os.zip + img, gapps.zip)

## Steps

1. Unlock bootloader (by enabling dev options -> OEM unlock)
2. Set default usb config as file transfer within dev options
3. Plug device into PC, register it with the RSA fingerprint
4. Boot into recovery mode by running ```$adb reboot recovery```
5. Wipe the device (best practice)
5. Depending on your recovery img, you can sideload the os.zip by: ```$adb sideload os.zip```. Take note of the slot letter (either A or B)
6. Once completed, depending on your recovery img, either do:
	i. Switch slots (TWRP) then reboot into recovery
	ii. Reboot into recovery (which switches slots for you, ie lineage recov img)
7. Go into Apply update -> Apply ADB -> ```$adb sideload gapps.zip```
8. Reboot system

Congratulations, you've successfully flashed a custom ROM on to your device!

## License

These instructions are licensed under [The MIT License (MIT)](LICENSE)
