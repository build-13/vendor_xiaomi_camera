## Leica Camera Configuration for Redmi Note 10

### How to?

1. Add this line to your BoardConfig.mk
```
# Inherit from proprietary files for Leica Camera
-include vendor/xiaomi/mojito-leicacamera/BoardConfigVendor.mk
```
2. And this line to your device.mk
```
# Call the Leica Camera setup
$(call inherit-product-if-exists, vendor/xiaomi/mojito-leicacamera/mojito-leicacamera-vendor.mk)
```
3. Clone this repository to vendor/xiaomi/mojito-leicacamera, preferably with `--depth=1` to avoid having a big size locally clone
```sh
git clone --depth=1 https://gitlab.com/pnplusplus/android_vendor_xiaomi_mojito-leicacamera vendor/xiaomi/mojito-leicacamera
```
4. Apply necessary *.patch in patch folder to respective ROM sources folder (Search in Google if you don't know how to apply a *.patch)
5. If you want to include Miui Gallery on your build, set environment variable below
```sh
export TARGET_USE_MIUI_GALLERY=true
```
and/or if you want to include Miui Scanner, set environment variable below
```sh
export TARGET_USE_MIUI_SCANNER=true
```
6. There's [recovery flashable](https://xdaforums.com/t/mods-fixes-for-custom-roms-mojito-sunny.4494371/post-89361948) version of Leica Camera. So, if you want to use it instead of building Leica Camera inlined with your ROM, set environment variable below
```sh
export TARGET_USE_LEICA_CAMERA=false
```
7. Start building and enjoy!

### Source

- https://xdaforums.com/t/useful-mods-for-custom-roms-mojito-sunny.4494371/
