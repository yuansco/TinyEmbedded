# TinyEmbedded - F1C200s Embedded Linux Development board

<img src="https://github.com/yuansco/TinyEmbedded/blob/master/Demo/01.Demo1.PNG" style="width:550px;"/>

The TinyEmbedded is a low-cost embedded Linux development board that features an ARM9-based F1C200s microprocessor with an integrated USB-to-UART serial console. Here are some highlights of this development board:

 * F1C200s: An ARM9-based microprocessor with an integrated 64MB DRAM.

 * On-board USB-to-UART serial console.

 * On-board LIS3DH acceleration sensor.

 * SSD1306-based 128x64 OLED display module.

 * One USB Type-A port.

 * Three indicator LEDs for power status, UART data transmission, and user-defined purposes.

 * Three buttons for reset, boot mode selection, and user-defined purposes.

 * One MicroSD slot for storing the boot image.

 * 16MB Serial NOR Flash.

 * AT24C02: A 2-kilobyte EEPROM.

After downloading the image to the SD card and starting the system, you can open the COM port via USB to view the boot logs of U-Boot and the Linux kernel. Once the system boots to the root filesystem, the OLED module will display 'Hi F1C200s'.

<img src="https://github.com/yuansco/TinyEmbedded/blob/master/Demo/02.Demo2.PNG" style="width:550px;"/>

### Hardware design

#### Block Diagram

<img src="https://github.com/yuansco/TinyEmbedded/blob/master/Document/01.Block_Diagram.PNG" style="width:450px;"/>

#### Power Tree

<img src="https://github.com/yuansco/TinyEmbedded/blob/master/Document/02.Power_Tree.PNG" style="width:450px;"/>

#### 3D view

<img src="https://github.com/yuansco/TinyEmbedded/blob/master/Document/03.3D_view.PNG" style="width:450px;"/>

#### Top view

<img src="https://github.com/yuansco/TinyEmbedded/blob/master/Document/04.TOP_view.PNG" style="width:450px;"/>

Schematic: [PDF](https://github.com/yuansco/TinyEmbedded/blob/master/Document/TinyEmbedded_VerB.pdf)

BOM: [CSV](https://github.com/yuansco/TinyEmbedded/blob/master/Document/BOM.CSV)

Image: [IMG](https://github.com/yuansco/TinyEmbedded/blob/master/Image/sysimage-sdcard.img)

### Build an SD card image for booting

Install necessary packages:
``` shell
sudo apt install wget unzip build-essential git bc swig libncurses-dev libpython3-dev libssl-dev
sudo apt install python3-distutils
```
Download BSP (Buildroot-based BSPs in another [repository](https://github.com/yuansco/buildroot-f1c200s)):
``` shell
git clone https://github.com/yuansco/buildroot-f1c200s.git
```
Apply defconfig and build image
``` shell
cd buildroot-tiny200
make f1c200s_dev_board_defconfig
make
```
