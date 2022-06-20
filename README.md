# android_device_realme_r5x
For building TWRP for Realme 5/5i/5s

TWRP device tree for Realme 5/5i/5s

## Features

Works:

- ADB
- Decryption of /data (Needs more testing)
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG
- Vibration support
- External sdcard

## Compile

First checkout minimal twrp with tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/realme/r5x" name="takumi021/device_realme_r5x-twrp" remote="github" revision="android-12.1" />
```

Finally execute these:

```
. build/envsetup.sh
lunch twrp_r5x-eng
make recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot flash recovery out/target/product/r5x/recovery.img
```

Then reboot to recovery

## Other Sources

Using precompiled stock kernel

## Thanks

