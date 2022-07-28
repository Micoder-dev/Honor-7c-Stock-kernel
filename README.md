Hello Guy's this is the kernel for HONOR 7C....

### Toolchain

Use this toolchain to avoid some errors => https://github.com/Micoder-dev/honor7c-kernel-4.9-toolchain.git

### Steps to compile.

1-> export ARCH=arm64 </br>
2-> export SUBARCH=arm64 </br>
3-> export CROSS_COMPILE=<path to toolchain 4.9>/bin/aarch64-linux-android- </br>
4-> make O=../out merge_msm8953_64_defconfig </br>
5-> make O=../out menuconfig </br>
6-> make O=../out CONFIG_NO_ERROR_ON_MISMATCH=y </br>

that's it your compilation begins...

After completing you can see a file on the out directory arch/arm64/boot/"Image.gz-dtb"

You can't flash that Image.gz-dtb file directly so you have to unpack and repack it on your KERNEL.img

As honor7c doesn't have a BOOT.img so don't try to search the boot image file there is only the kernel.img you have to unpack the KERNEL.img file using Android Image Kitchen, after unpacking you can see a folder named split_img, in that folder you can see a file named as "KERNEL.img-kernel" that is the file that you have to replace with your compiled Image.gz-dtb. After replacing the file now you repackn it, so now you will get a new image file... you can flash the new img on fastboot by using this command -> "fastboot flash kernel image-new.img"

### Custom Kernerls

I have compiled a Nethunter Kernel for Huawei Honor 7C you can flash it by following the above steps </br>
Nethunter Kernel => https://github.com/Micoder-dev/Honor7c_Nethunter_kernel.git
