# local_manifests

To build my specific LOS 14.1 'microG & sec.enhanced' version for the 
Osprey, Falcon and SM-T815 device, follow the steps below:

## Setup build tree
Create the directory, which should hold your build tree, 'cd' into it
and run the following commands:
```Shell session
repo init -u https://github.com/LineageOS/android.git -b cm-14.1
cd .repo
git clone https://github.com/lin14-mGoms/local_manifests
cd local_manifests
git checkout cm-14.1-microG
cd ../..
repo sync
```

## Prepare build / apply patches
cd into directory **z_patches** and execute the script `./patches_apply.sh`

Create a build script in the root dir of your build tree, take the
sample scripts in directory z_patches as reference and adapt them according
to your needs.

## Differences to 'vanilla' LineageOS 14.1
1. Fork of LineageOS Jelly browser (Qwant and StartPage as addl. search engines)
2. Osprey-device only: Use Squid Kernel (oreo branch)
3. 'microG build' having the following features:
   - Prebuilt 'microG' apps included
   - Enhanced SELinux policies (restrict /proc timers and /proc/net)
   - Additional AppOps (Sensor, Storage) in Privacy Guard
   - SQLite Secure delete feature

## In case you would like to build the osprey device
You need the Linaro GCC 7.3 cross compiler to build the kernel! Get it either from the Linaro web site or build it yourself.
To build yourself, clone the https://github.com/nathanchance/build-tools-gcc repository and run the ./build script afterwards.
Take the build_opsprey.sh script and adapt its location accordingly!
