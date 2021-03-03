# android_device_xiaomi_apollo
Device tree for Xiaomi Mi 10T / 10T Pro / Redmi K30S Ultra (codenamed: "apollo")

*STATUS: BETA*

The Xiaomi Mi 10T serie are high-end smartphones from Xiaomi and was announced and released in October 2020.


## Device specifications

| Device       | Xiaomi Mi 10T / 10T Pro / Redmi K30S        |
| -----------: | :------------------------------------------ |
| SoC          | Qualcomm SM8250 Snapdragon 865              |
| CPU          | 8x Qualcomm® Kryo™ 585 up to 2.84GHz        |
| GPU          | Adreno 630                                  |
| Memory       | 8GB (LPDDR5)                                |
| Shipped Android version | 10                               |
| Storage      | 128GB / 256GB UFS 3.1 flash storage         |
| Battery      | Non-removable Li-Po 5000mAh                 |
| Dimensions   | 165.1 x 76.4 x 9.3 mm                       |
| Display      | 2400 x 1080 (20:9), 6.67 inch               |

## Features

**Works**

- Booting
- Data decryption
- Vibration
- ADB
- Adb side load

**Not Works**
- Installation problem on K30S Ultra, build is now ONLY suitable for Global versions of apollo
- Apex mount issues - ignore it

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-10.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/apollo" name="ChrisMiller94/android_device_xiaomi_apollo" remote="github" revision="android-10.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_apollo-eng
export ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
mka recoveryimage 
```

To test it:

```
fastboot boot out/target/product/apollo/recovery.img
```

## Copyright notice

/*
 *  Copyright (C) 2020-2021 The OrangeFox Recovery Project
 *
 * This program is free software: you can redistribute it and/or modify
 * it under the terms of the GNU General Public License as published by
 * the Free Software Foundation, either version 3 of the License, or
 * (at your option) any later version.
 *
 * This program is distributed in the hope that it will be useful,
 * but WITHOUT ANY WARRANTY; without even the implied warranty of
 * MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 * GNU General Public License for more details.
 *
 * You should have received a copy of the GNU General Public License
 * along with this program.  If not, see <http://www.gnu.org/licenses/>.
 */


## Thanks
- [mauronofrio](https://github.com/mauronofrio)
- [Whyle] (https://github.com/Whyle)
