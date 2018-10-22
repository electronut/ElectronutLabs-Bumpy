# Building firmware

These instructions are for linux. First, clone [bumpy firmware](git@github.com:electronut/blackmagic.git). Then `cd blackmagic` and run:

    make PROBE_HOST=bumpy

The directory `src` will contain the binaries.

If you have an older Bumpy, you may want to upgrade DFU, follow these instructions after downloading the correct files.

[dfu_upgrade.bin](https://github.com/electronut/ElectronutLabs-Bumpy/releases/download/v1.2/dfu_upgrade.bin)

[blackmagic_dfu.bin](https://github.com/electronut/ElectronutLabs-Bumpy/releases/download/v1.2/blackmagic_dfu.bin)

[blackmagic.bin](https://github.com/electronut/ElectronutLabs-Bumpy/releases/download/v1.2/blackmagic.bin)

```
1. Prepare bootloader update
Normal BMP has to be replaced by the upgrade program:
    dfu-util -s 0x08002000:leave -D dfu_upgrade.bin
Wait until Dual color led flashes red, indicating DFU is active for the
bootloader.

2. Flash new bootloader
    dfu-util -s 0x08000000 -D blackmagic_dfu.bin
Wait until Dual color led flashes green, indicating bootloader is active.

If not, unplug USB, keep black reset button pressed, replug USB.
Wait until Dual color led flashes green.

3. Flash BMP
    dfu-util -s 0x08002000:leave:force -D blackmagic.bin
```

# Releases

## Version 1.2

Download [link](https://github.com/electronut/ElectronutLabs-Bumpy/releases/download/v1.2/blackmagic.bin)

## Version 1.1

Download [link](https://github.com/electronut/ElectronutLabs-Bumpy/releases/download/v1.1/bumpy-rev1.1.bin)
