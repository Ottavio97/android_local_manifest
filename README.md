Local manifests to build PacRom 12.1 for [Chuwi Hi10 Plus](http://konstakang.com/devices/chuwi_vi10plus/CM12.1)

How to build:
-------------

Initialize repo:

    repo init -u git://github.com/PAC-ROM/pac-rom.git -b pac-5.1 --depth=1 -groups=all,-notdefault,-device,-darwin,-mips,-exynos5
    curl --create-dirs -L -o .repo/local_manifests/manifest_intel_cherrytrail.xml -O -L https://raw.githubusercontent.com/Ottavio97/android_local_manifest/pac/manifest_intel_cherrytrail.xml
    repo sync -c

### Chuwi Hi10 Plus:

    curl -L -o .repo/local_manifests/manifest_intel_chuwi_hi10plus.xml -O -L https://raw.githubusercontent.com/Ottavio97/android_local_manifest/pac/manifest_intel_chuwi_hi10plus.xml
    repo sync

Compile:

    . build/envsetup.sh
    brunch chuwi_hi10plus
