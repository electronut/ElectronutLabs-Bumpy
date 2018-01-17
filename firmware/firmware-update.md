## Instructions to perform a firmware update on Bumpy.

The instructions mentioned in this document, allow performing a firmware update via USB.

## Setup

* Extract the contents of **dfu-util-0.9-win64.zip** file included in **softwares** directory.

* Add the location of **dfu-util.exe** executable, available in the extracted folder from above, and add it to your
path variables.

* Ensure that dfu-util is part of your PATH variables by simply running a command prompt and typing **dfu-util**.

* Plug-in Bumpy. Wait until the onboard red LED turns on.

* Run: **Zadig**, available in **softwares** directory.

* Select: **Black Magic Firmware Upgrade (STLINK) (Interface 4)** from the drop down menu.

* If no device is available for selection, go to: Options > List All Devices.

* Select **WinUSB** driver and click on **Install**.

* The above steps have enabled firmware update functionality over USB.

* Now, check that you are in the same directory as the **bumpy-rev1.1.bin**

* Issue: `dfu-util -d 1d50:6018,:6017 -s 0x08002000:leave -D bumpy-rev1.1.bin`.

* Wait for firmware to load. The expected output is shown below:

![](firmware-update.png)

* Remove Bumpy and plugin again, to reset the chip.

The firmware has been updated successfully.
