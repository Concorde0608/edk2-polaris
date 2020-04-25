
Attempt to create a minimal EDK2 for Xiaomi MIX 2s.

Based on fxsheep's port for Pixel3XL (https://github.com/fxsheep/edk2-sagit).

## Status 

It is still beginning. 😂

### Working

...

### Not Working

...

## Building
Tested on WSL2.

First, clone EDK2.

```
cd ..
git clone https://github.com/tianocore/edk2.git --recursive
git clone https://github.com/tianocore/edk2-platforms.git
```

You should have all three directories side by side.

Next, install dependencies:

WSL2:

```
sudo apt install build-essential uuid-dev iasl git nasm python python-pip python3-distutils gcc-aarch64-linux-gnu abootimg p7zip
sudo pip install uefi_firmware
```

Also see [EDK2 website](https://github.com/tianocore/tianocore.github.io/wiki/Using-EDK-II-with-Native-GCC#Install_required_software_from_apt)

Then, extract the XBL binary from your device (the powerful dd will serve you), name it xbl.elf and put it to current directory.
Execute ./extract-xbl.sh to get the proprietary blobs extracted:

```
./extract-xbl.sh
```

Finally, ./build.sh.

Then fastboot boot uefi.img.

# Credits

This is based on zhuowei's [edk2-pixel3](https://github.com/Pixel3Dev/edk2-pixel3).  
SimpleFbDxe screen driver is from imbushuo's [Lumia950XLPkg](https://github.com/WOA-Project/Lumia950XLPkg).  
Special thanks to @lemon1ice, @gus33000, @fxsheep and @imbushuo for guidance.  