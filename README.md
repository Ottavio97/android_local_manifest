Local manifests to build Resurrection Remix 5.5.9 for [Chuwi Hi10 Plus](http://konstakang.com/devices/chuwi_vi10plus/CM12.1)

How to build:
-------------

Initialize repo:

    repo init -u git://github.com/ResurrectionRemix/platform_manifest.git -b optimized-lollipop5.1
    curl --create-dirs -L -o .repo/local_manifests/manifest_intel_cherrytrail.xml -O -L https://raw.githubusercontent.com/Ottavio97/android_local_manifest/rr-559/manifest_intel_cherrytrail.xml
    repo sync

### Chuwi Vi10 Plus:

    curl -L -o .repo/local_manifests/manifest_intel_chuwi_hi10plus.xml -O -L https://raw.githubusercontent.com/Ottavio97/android_local_manifest/rr-559/manifest_intel_chuwi_hi10plus.xml
    repo sync

Download and install poky toolchain to its default location (/opt/poky/1.8):

    wget http://downloads.yoctoproject.org/releases/yocto/yocto-1.8/toolchain/x86_64/poky-glibc-x86_64-core-image-sato-core2-64-toolchain-1.8.sh
    sudo ./poky-glibc-x86_64-core-image-sato-core2-64-toolchain-1.8.sh

Compile:

    . build/envsetup.sh
    brunch chuwi_hi10plus
