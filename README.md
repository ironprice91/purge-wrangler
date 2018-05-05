![Header](https://raw.githubusercontent.com/mayankk2308/purge-wrangler/master/resources/header.png)

![macOS Support](https://img.shields.io/badge/macOS-10.13.4+-orange.svg?style=for-the-badge) ![Github All Releases](https://img.shields.io/github/downloads/mayankk2308/purge-wrangler/total.svg?style=for-the-badge)
# PurgeWrangler
This script enables external graphics on Thunderbolt 1/2 Macs, which is actively blocked in macOS **10.13.4**.

## Requirements
This script requires the following specifications:
* Mac with **Thunderbolt**
* **macOS 10.13.4** or later
* System Backup

It is recommended that you have a backup of the system. Testing was done on a **Mid-2014 MacBook Pro w/ GeForce GT 750M**.

## Usage
Please follow these steps:

### Step 1
Disable **system integrity protection** for macOS using **Terminal** in **Recovery**:
```bash
$ csrutil disable
$ reboot
```

### Step 2
Boot back into macOS, then copy-paste the following into **Terminal**:
```bash
curl -L -s https://github.com/mayankk2308/purge-wrangler/releases/download/3.0.0/purge-wrangler.sh > purge-wrangler.sh;chmod +x purge-wrangler.sh;./purge-wrangler.sh;rm purge-wrangler.sh
```

Note that you may change **3.0.0** to a different valid version in the above command.

Alternatively, download [purge-wrangler.sh](https://github.com/mayankk2308/purge-wrangler/releases). Then run the following in **Terminal**:
```bash
$ cd Downloads
$ chmod +x purge-wrangler.sh
$ ./purge-wrangler.sh
```

You will be prompted to enter your account password for **superuser permissions**. On first-time use, the script will auto-install itself as a binary into `/usr/local/bin/`. This enables much simpler future use - simply type in `purge-wrangler` in Terminal. Note that versions prior to **3.0.0** do not have auto-install capability.

## Options
The script provides users with a variety of options in an attempt to be as user-friendly as possible.

### 1. TB1/2 eGPU Patch
Enables default eGPU support on **Thunderbolt 1/2** macs.

### 2. Universal NVIDIA eGPU Patch
Enables NVIDIA eGPUs on **any** mac, regardless of **Thunderbolt** version.

### 3. Patch Status Check
Checks for the applied patches and provides system state information

### 4. Uninstall Patches
In-place uninstaller for the patches.

### 5. System Recovery
Recover original untouched macOS configuration prior to script modifications.

### 6. Command-Line Shortcuts
Prints a list of single-letter options that may be passed to the script or binary to completely forgo the command-line user interface and directly perform actions.

### 7. Script Version
Prints the version of the script/binary.

### 8. Disable Hibernation
Disables hibernation mode and automatic power off as these settings may resolve wake-up failures with discrete graphics disabled.

### 9. Enable Hibernation
Restores the hibernation mode configurations to recommended settings.

### 10. Reboot System
Reboots the system with a countdown.

## Troubleshooting
If you are unable to boot into macOS, boot while pressing **CMD + S**, then enter the following commands:
```bash
$ mount -uw /
$ cd /path/to/script/
$ purge-wrangler
```

## References
Many thanks to **@itsage**, **@fricorico**, **@goalque**, and many others at [egpu.io](https://egpu.io) for the insightful discussion that led me to the fix.

## Disclaimer
This script moves core system files associated with macOS. While any of the potential issues with its application are recoverable, please use this script at your discretion. I will not be liable for any damages to your operating system.

## License
See the license file for more information.

## Donate
A *"Thank you"* is enough to make me smile. But due to popular demand:

[![paypal][image-1]][1]

Knock yourself out :)

[image-1]:	https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif
[1]:	https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=mayankk2308@gmail.com&lc=US&item_name=mac_editor&no_note=0&currency_code=USD&bn=PP-DonationsBF:btn_donate_SM.gif:NonHostedGuest
