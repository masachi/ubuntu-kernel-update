# ubuntu-kernel-update

=================

Bash script for Ubuntu (and derivatives as LinuxMint) to easily (un)install kernels from the [Ubuntu Kernel PPA](http://kernel.ubuntu.com/~kernel-ppa/mainline/).

Install
----------------
```
apt install wget
wget https://raw.githubusercontent.com/masachi/ubuntu-kernel-update/main/kernel-update.sh
chmod +x kernel-update.sh

```

Usage
-----------------
```
Usage: kernel-update.sh -c|-l|-r|-u

Download & install the latest kernel available from kernel.ubuntu.com

Arguments:
  -c               Check if a newer kernel version is available
  -i [VERSION]     Install kernel VERSION, see -l for list. You don't have to prefix
                   with v. E.g. -i 4.9 is the same as -i v4.9. If version is
                   omitted the latest available version will be installed
  -l [SEARCH]      List locally installedkernel versions. If an argument to this
                   option is supplied it will search for that
  -r [SEARCH]      List available kernel versions. If an argument to this option
                   is supplied it will search for that
  -u [VERSION]     Uninstall the specified kernel version. If version is omitted,
                   a list of max 10 installed kernel versions is displayed
  -h               Show this message

Optional:
  -p, --path DIR       The working directory, .deb files will be downloaded into
                       this folder. If omitted, the folder /tmp/ubuntu-mainline-kernel.sh/
                       is used. Path is relative from $PWD
  -ll, --low-latency   Use the low-latency version of the kernel, only for amd64 & i386
  -lpae, --lpae        Use the Large Physical Address Extension kernel, only for armhf
  --snapdragon         Use the Snapdragon kernel, only for arm64
  -do, --download-only Only download the deb files, do not install them
  -ns, --no-signature  Do not check the gpg signature of the checksums file
  -nc, --no-checksum   Do not check the sha checksums of the .deb files
  -d, --debug          Show debug information, all internal commands echo their output
  --rc                 Also include release candidates
  --yes                Assume yes on all questions (use with caution!)
```

Elevated privileges
-------------------

This script needs elevated privileges when installing or uninstalling kernels.

Either run this script with sudo or configure the path to sudo within the script to sudo automatically
