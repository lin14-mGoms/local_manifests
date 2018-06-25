# local_manifests

To build my specific LOS 14.1 'microG-patched & oms-enabled' version for the 
Osprey, Falcon and SM-T815 device, follow the steps below:

## Setup build tree
Create the directory, which should hold your build tree, 'cd' into it
and run the following commands:
```Shell session
repo init -u https://github.com/LineageOS/android.git -b cm-14.1
cd .repo
git clone https://github.com/cm13-microG/local_manifests
cd local_manifests
git checkout cm-14.1-oms
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
3. Removed below packages from the build:
   - **CMUpdater** (unofficial build, so no update server)
4. Patched for 'microG' (see microg.org)
5. OMS enabled build (compatible to 'substratum')
