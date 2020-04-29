# local_manifests

To build my specific LineageOS 14.1 version for the Osprey, Falcon, Peregrine and SM-T815 device, follow the steps below:

## Setup build tree
Create the directory, which should hold your build tree, 'cd' into it
and run the following commands:
```Shell session
repo init -u https://github.com/LineageOS/android.git -b cm-14.1
cd .repo
git clone https://github.com/lin14-mGoms/local_manifests
cd local_manifests
git checkout cm-14.1
cd ../..
repo sync
```

## Prepare build / apply patches
cd into directory **z_patches** and execute the script `./patches_apply.sh`

Create a build script in the root dir of your build tree, take the
sample scripts in directory z_patches as reference and adapt them according
to your needs.

## Differences to 'vanilla' LineageOS 14.1
1. Fork of LineageOS **Jelly** browser (Qwant and StartPage as addl. search engines)
2. Osprey-device only: Use **Squid Kernel** (oreo branch)
3. If you have applied the patches in the z_patches directory: microG-patch

## In case you would like to build the osprey device
You need the Linaro GCC 7.3 cross compiler to build the kernel! 
If you have followed the above instructions, this will be already the case as part of the build tree and configuration.
