# PixelExperience Plus for Redmi Note 10 Pro/Pro+/Discrovery (ruby) #
You can build PixelExperience thirteen-plus for ruby as follows.
### Sync ###

```bash

# Initialize local repository
repo init -u https://github.com/PixelExperience/manifest -b thirteen-plus

# Sync
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```
### Clone device specific stuff ###
```bash
git clone https://github.com/kasun-97/android_device_xiaomi_ruby.git -b pe device/xiaomi/ruby
git clone https://github.com/PQEnablers-Devices/android_kernel_xiaomi_mt6877.git -b lineage-20 kernel/xiaomi/mt6877
git clone https://github.com/PQEnablers-Devices/android_vendor_xiaomi_ruby -b lineage-20 vendor/xiaomi/ruby

git clone https://github.com/PixelExperience/hardware_xiaomi -b thirteen hardware/xioami
git clone https://github.com/PixelExperience/hardware_mediatek.git -b thirteen hardware/mediatek
git clone https://github.com/PixelExperience/device_mediatek_sepolicy_vndr.git -b thirteen device/mediatek/sepolicy_vndr
```

### Build ###

```bash

# Set up environment
$ . build/envsetup.sh

# Choose a target
$ lunch aosp_ruby-userdebug

# Build the code
$ mka bacon -j$(nproc --all)
```
