# Installing CyberBackup on AltLinux
This section describes how to install CyberBackup on AltLinux Distro in detail.

Important! These instructions only cover the installation of CyberBackup, not how to activate it. You will have to figure that out yourself.

## Preparation
### List of libraries
- gcc
- make
- kernel-headers-modules-`<core-version>`
- update-kernel
- perl
- dkms
- libelf-devel

### Kernel
Find out the kernel version with the following command:
```bash
[admin@srv ~]$ uname -r
6.12.65-6.12-alt1
[admin@srv ~]$
```
Take only the first two numbers, i.e. 6.12 in my case.

### Installing packages
You can install the packages with the following command:
```bash
[admin@srv ~]$ su -
Password: 
[root@srv ~]# apt-get update && apt-get install gcc make update-kernel perl dkms libelf kernel-headers-modules-<core-version> -y
```
Replace <core-version> with your kernel version, as mentioned in the "Kernel" section.

After installing the packages, run the following command to generate the kernel source code:
```bash
[root@srv ~]# update-kernel
```

Then restart the device.

### Installing CyberBackup
Go to the [CyberProtect](https://www.acronis.com/en/support/protect/15/) website.

Download the installer for Linux. Not ISO.

After downloading the installer, make it executable:
```bash
[admin@srv ~]$ chmod +x CyberBackup_18_64-bit.x86_64
```

And run it in Sudo mode.

Next, select the packages you need, and Profit, CyberBackup is installed.
