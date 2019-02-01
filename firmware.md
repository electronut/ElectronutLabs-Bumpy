# Building firmware

These instructions are for linux. First, clone bumpy firmware `git clone git@github.com:electronut/blackmagic.git -b bumpy`. Then `cd blackmagic` and run:

    make PROBE_HOST=bumpy

The directory `src` will contain the binaries.

To upload a specific version of firmware:
	
	dfu-util -s 0x08002000:leave:force -D blackmagic.bin

# Releases

We recommend using version v1.3 firmware, it has support for Nrf52840 and newer chip IDs for Nrf52832 etc., but automatic reset upon disconnect from GDB doesn't work in this one (though you can do `run` inside GDB to run the code). V1.2 is here for archival reasons.

## Version 1.3

Download [link](https://github.com/electronut/ElectronutLabs-Bumpy/releases/download/v1.3/blackmagic.bin)

## Version 1.2

Download [link](https://github.com/electronut/ElectronutLabs-Bumpy/releases/download/v1.2/blackmagic.bin)

## Version 1.1

Download [link](https://github.com/electronut/ElectronutLabs-Bumpy/releases/download/v1.1/bumpy-rev1.1.bin)
