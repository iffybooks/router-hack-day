[Notes for Router Hack Day 2]{.c8 .c10}

[![](images/image1.png){style="width: 128.07px; height: 93.87px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 128.07px; height: 93.87px;"}

[]{.c15 .c13 .c8}

[Access your router's serial shell]{.c13 .c8 .c15}

[Disassemble your router. You'll need to remove a screw on the bottom,
which is covered by a sticker.]{.c0}

[Cut the ends off three DuPont jumper wires, leaving port connectors on
the other ends.]{.c0}

[Solder the stripped wires to the terminal points pictured below,
located in the middle of the circuit board.]{.c0}

Connect the terminal labeled [Tx]{.c8} in the image above to the pin
labeled [Rx]{.c8} on your USB serial interface. Next, connect
[Rx]{.c8} from the router to [Tx]{.c8} on the USB serial interface. Then
connect [GND]{.c8} to
[GND]{.c8}[.]{.c0}[![](images/image14.png){style="width: 269.47px; height: 222.53px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 269.47px; height: 222.53px;"}

[![](images/image6.png){style="width: 226.33px; height: 296.47px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 226.33px; height: 296.47px;"}

[Plug the USB serial interface into your computer.]{.c0}

[Plug in the router.]{.c0}

[Run the following command to see if your USB serial interface is
connected.]{.c0}

[ls /dev/ttyUSB\*]{.c7 .c20}

[sudo apt-get autoremove brltty]{.c0}

[You can use these commands to get info about connected USB
devices:]{.c0}

[lsusb]{.c0}

[dmesg]{.c0}

[Command for opening serial connection with router:]{.c0}

[minicom -D /dev/ttyUSB0 -c on]{.c0}

Press CTRL+A, then press O to open the configuration menu. Use the arrow
keys to select [Serial port setup]{.c8}[. Press enter.]{.c18}

[![](images/image3.png){style="width: 664.80px; height: 373.93px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 664.80px; height: 373.93px;"}

Press [F]{.c8} to switch [Hardware Flow Control]{.c8} to
[No]{.c8}[.]{.c0}

[Before:]{.c0}

[![](images/image2.png){style="width: 452.51px; height: 310.30px; margin-left: -28.28px; margin-top: -46.40px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 231.13px; height: 205.40px;"}[ ]{.c0}

[After:]{.c0}

[![](images/image5.png){style="width: 455.03px; height: 310.37px; margin-left: -28.08px; margin-top: -46.35px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 233.80px; height: 205.53px;"}

Press [enter]{.c8}[ to close the serial port setup menu.]{.c0}

To save this setting as your default, use the down arrow to select [Save
setup as dfl]{.c8}[. Press enter to save.]{.c0}

[![](images/image4.png){style="width: 448.34px; height: 281.45px; margin-left: -16.39px; margin-top: -5.01px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 326.07px; height: 263.00px;"}

Use the arrow keys to select [Exit]{.c8}, then press
[enter]{.c8}[.]{.c0}

[Press enter and you'll be prompted to log in.]{.c0}

[username: root]{.c0}

[password: Fireitup]{.c0}

Press [tab]{.c8}[ twice in a row to see a list of available
software.]{.c0}

[Restart your router while the USB serial connector is attached and
you'll see a waterfall of interesting startup info:]{.c0}

[![](images/image8.png){style="width: 495.66px; height: 276.25px; margin-left: -3.98px; margin-top: -5.75px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 476.20px; height: 258.73px;"}

To get your router's SSID name, use the command [wl status]{.c8}[.]{.c0}

[![](images/image7.png){style="width: 427.80px; height: 238.48px; margin-left: -2.96px; margin-top: -4.28px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 410.80px; height: 223.40px;"}

[Creating 8 MTD partitions on \"sflash\":]{.c0}

[\[what\'s on the flash device\]]{.c0}

[binwalk -Me \.....bin]{.c0}

[CRC value tells us the checksum of everything after HDR0]{.c0}

[OpenWRT has tools to do this.]{.c0}

[dd for manipulating the firmware]{.c0}

[40 hex bytes at a time, but skip first 40 bytes:]{.c0}

[dd if=US_FH1201V1.0BR_V1.2.0.14\\(408\\)\_EN_RD.bin of=data
bs=\$((0x40)) skip=1]{.c0}

[In CFE mode, give yourself an IP address]{.c0}

[Like 192.168.1.X]{.c0}

[Then go to 192.168.1.1 and upload TRX firmware file]{.c0}

[Remove]{.c0}

[TRX format starts with HR0 in all caps]{.c0}

[trx format]{.c0}

[\#########]{.c0}

[Mount file system in serial shell:]{.c0}

[mount -t usbfs none /proc/bus/usb/]{.c0}

[Show connected USB devices:]{.c0}

[cat /proc/bus/usb/]{.c0}

[Do a web search for vendor id number and prodID number to get the chip
details]{.c0}

[Wireless adapter:]{.c0}

[BCM43526]{.c0}

[\[SOIC8]{.c0}

[square next to serial connectors, which contains the firmware]{.c0}

[\]]{.c0}

[SOIC:]{.c0}

[25q64b]{.c0}

[\[CH341 is the tool to flash the firmware chip itself\]]{.c0}

[Main CPU:]{.c0}

[BCM5357]{.c0}

[32-bit little endian]{.c0}

[go to buildroot dir]{.c0}

[make menuconfig]{.c0}

[target options \-- MIPS little endian]{.c0}

[toolchain \--\> change c compiler to musl]{.c0}

[build options \--\> switch libraries to static only]{.c0}

[target packages -\> networking applications -\> enable tcpdump (press
space)]{.c0}

[save and exit]{.c0}

[make tcpdump]{.c0}

[Download router firmware]{.c2}

[Here's the stock firmware that comes with the router:]{.c0}

[Atlas Media AMW-DBR1200AC Firmware:]{.c6}

[             
]{.c7}[[https://iffybooks.net/wp-content/uploads/2023/05/AtlasMedia_AC1200_FirmwareV1.4.bin](https://www.google.com/url?q=https://iffybooks.net/wp-content/uploads/2023/05/AtlasMedia_AC1200_FirmwareV1.4.bin&sa=D&source=editors&ust=1687491815732647&usg=AOvVaw35NOxv89RdpF5V6RBdIUHF){.c12}]{.c4}

[And here are two firmware releases from Tenda that work with the
router. You'll need to extract the files after downloading.]{.c0}

[Tenda FH1201 Firmware V1.2.0.8_EN:]{.c13 .c16 .c8}[ \
           
 ]{.c7}[[h](https://www.google.com/url?q=https://www.tendacn.com/us/download/detail-2123.html&sa=D&source=editors&ust=1687491815733143&usg=AOvVaw3FdE1pvtPm-j5gr5-SM4cH){.c12}]{.c1
.c8
.c16}[[ttps://www.tendacn.com/us/download/detail-2123.html](https://www.google.com/url?q=https://www.tendacn.com/us/download/detail-2123.html&sa=D&source=editors&ust=1687491815733321&usg=AOvVaw2ALaB24KgMalevRccKuXjJ){.c12}]{.c4}

[Tenda FH1206 Firmware V1.2.0.8(8155)\_EN:]{.c6}

[             
]{.c7}[[https://www.tendacn.com/us/download/detail-2344.html](https://www.google.com/url?q=https://www.tendacn.com/us/download/detail-2344.html&sa=D&source=editors&ust=1687491815733587&usg=AOvVaw1MbjtlTtHl8R5TLIhDThV1){.c12}]{.c4}

Download the [[Tenda
FH1206](https://www.google.com/url?q=https://www.tendacn.com/us/download/detail-2344.html&sa=D&source=editors&ust=1687491815733826&usg=AOvVaw3GSgpqA29tuHjrpWse8HSo){.c12}]{.c1}[ firmware,
or your firmware of choice from the list above.]{.c0}

Decompress the
[[RAR](https://www.google.com/url?q=https://en.wikipedia.org/wiki/RAR_(file_format)&sa=D&source=editors&ust=1687491815734065&usg=AOvVaw14-VebMCdiThVr9G98d92O){.c12}]{.c1} files
you downloaded from Tenda's site, giving you a firmware file with a name
like [US_FH1206V1.0BR_V1.2.0.8(8155)\_EN_TD.bin]{.c8}[. If you don't
already have a program installed for decompressing RAR files, you can
use one of the following:]{.c0}

[        ]{.c17 .c8}[MacOS:]{.c13 .c8} [The Unarchiver]{.c18
.c23} [[https://theunarchiver.com](https://www.google.com/url?q=https://theunarchiver.com/&sa=D&source=editors&ust=1687491815734442&usg=AOvVaw0ZRgVfVXTzXhjTE8J7HuR5){.c12}]{.c1}

[        ]{.c17 .c8}[Windows:]{.c13 .c8} WinRAR
[[https://www.win-rar.com](https://www.google.com/url?q=https://www.win-rar.com/&sa=D&source=editors&ust=1687491815734764&usg=AOvVaw3s5jRtvU_JSLzsYkPRWYaf){.c12}]{.c1}

[        ]{.c8 .c17}[Linux:]{.c8 .c13} unrar
[[https://linux.die.net/man/1/unrar](https://www.google.com/url?q=https://linux.die.net/man/1/unrar&sa=D&source=editors&ust=1687491815735080&usg=AOvVaw3mjD2T5OHci2OIcO2uNDK1){.c12}]{.c1}

[Upload new firmware through the router admin panel]{.c8 .c9}

[ ]{.c0}

[![](images/image10.png){style="width: 664.80px; height: 373.93px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 664.80px; height: 373.93px;"}

[![](images/image9.png){style="width: 664.80px; height: 373.93px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 664.80px; height: 373.93px;"}

[![](images/image9.png){style="width: 664.80px; height: 373.93px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 664.80px; height: 373.93px;"}

[![](images/image11.png){style="width: 664.80px; height: 373.93px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 664.80px; height: 373.93px;"}

[Decompress the router firmware]{.c2}

[These instructions are from Jim. Thanks, Jim!]{.c0}

[clone the repo]{.c0}

[git clone https://github.com/devttys0/sasquatch.git]{.c0}

[then cd in to sasquatch directory]{.c0}

[the README mentions this as a pre-req, so do this]{.c0}

[sudo apt-get install build-essential liblzma-dev liblzo2-dev
zlib1g-dev]{.c0}

[if you run ./build.sh at this point you will get a bunch of errors
related to xz_wrapper and LZMA]{.c0}

[eventually it ends in something like this:]{.c0}

[xz_wrapper.c:462:20: error: 'LZMA_BUF_ERROR' undeclared (first use in
this function)]{.c0}

[  462 \|   } else if(res != LZMA_BUF_ERROR)]{.c0}

[      \|                    \^\~\~\~\~\~\~\~\~\~\~\~\~\~]{.c0}

[xz_wrapper.c: In function 'xz_uncompress':]{.c0}

[xz_wrapper.c:494:2: error: unknown type name 'lzma_ret']{.c0}

[  494 \|  lzma_ret res = lzma_stream_buffer_decode(&memlimit, 0,
NULL,]{.c0}

[      \|  \^\~\~\~\~\~\~\~]{.c0}

[xz_wrapper.c:494:17: error: implicit declaration of function
'lzma_stream_buffer_decode'
\[-Werror=implicit-function-declaration\]]{.c0}

[  494 \|  lzma_ret res = lzma_stream_buffer_decode(&memlimit, 0,
NULL,]{.c0}

[      \|                
\^\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~\~]{.c0}

[xz_wrapper.c:497:12: error: 'LZMA_OK' undeclared (first use in this
function)]{.c0}

[  497 \|  if(res == LZMA_OK && size == (int) src_pos)]{.c0}

[      \|            \^\~\~\~\~\~\~]{.c0}

[xz_wrapper.c:503:1: error: control reaches end of non-void function
\[-Werror=return-type\]]{.c0}

[  503 \| }]{.c0}

[      \| \^]{.c0}

[cc1: all warnings being treated as errors]{.c0}

[make: \*\*\* \[\<builtin\>: xz_wrapper.o\] Error 1]{.c0}

[open the patch file in ./patches/patch0.txt and find this section]{.c0}

[ # To build using XZ Utils liblzma - install the library and
uncomment]{.c0}

[ # the XZ_SUPPORT line below.]{.c0}

[ #]{.c0}

[-#XZ_SUPPORT = 1]{.c0}

[+XZ_SUPPORT = 1]{.c0}

[It will be around line 38087 of the 38726, so pretty close to the
bottom of the file]{.c0}

[change the line from]{.c0}

[+XZ_SUPPORT = 1]{.c0}

[to]{.c0}

[+XZ_SUPPORT = 0]{.c0}

[then run ./build.sh again]{.c0}

[this time it works successfully and end in something like this]{.c0}

[make\[1\]: Entering directory
\'/AC1200/sasquatch/squashfs4.3/squashfs-tools/LZMA/lzmadaptive/C/7zip/Compress/LZMA_Lib\']{.c0}

[make\[1\]: Nothing to be done for \'all\'.]{.c0}

[make\[1\]: Leaving directory
\'/AC1200/sasquatch/squashfs4.3/squashfs-tools/LZMA/lzmadaptive/C/7zip/Compress/LZMA_Lib\']{.c0}

[cc -g -O2  -I. -I./LZMA/lzma465/C -I./LZMA/lzmalt
-I./LZMA/lzmadaptive/C/7zip/Compress/LZMA_Lib -D_FILE_OFFSET_BITS=64
-D_LARGEFILE_SOURCE -D_GNU_SOURCE -DCOMP_DEFAULT=\\\"gzip\\\" -Wall
-Werror  -DGZIP_SUPPORT -DLZMA_SUPPORT -DLZO_SUPPORT -DXATTR_SUPPORT
-DXATTR_DEFAULT   -c -o lzma_wrapper.o lzma_wrapper.c]{.c0}

[g++   ./LZMA/lzmalt/\*.o unsquashfs.o unsquash-1.o unsquash-2.o
unsquash-3.o unsquash-4.o swap.o compressor.o unsquashfs_info.o
gzip_wrapper.o lzma_wrapper.o ./LZMA/lzma465/C/Alloc.o
./LZMA/lzma465/C/LzFind.o ./LZMA/lzma465/C/LzmaDec.o
./LZMA/lzma465/C/LzmaEnc.o ./LZMA/lzma465/C/LzmaLib.o lzo_wrapper.o
read_xattrs.o unsquashfs_xattr.o -lpthread -lm -lz
-L./LZMA/lzmadaptive/C/7zip/Compress/LZMA_Lib -llzmalib   -llzo2 -o
sasquatch]{.c0}

[mkdir -p /usr/local/bin]{.c0}

[cp sasquatch /usr/local/bin]{.c0}

[now when you run binwalk on the firmware dump file it will extract as
expected]{.c0}

[binwalk -eM flash.bin]{.c0}

[now the squashfs-root directory contains the files from the
router]{.c0}

[notably, check out the passwd and shadow files]{.c0}

[\$ find . \| egrep \"passwd\|shadow\"]{.c0}

[./squashfs-root/etc_ro/passwd]{.c0}

[./squashfs-root/etc_ro/passwd_private]{.c0}

[./squashfs-root/etc_ro/shadow]{.c0}

[./squashfs-root/etc_ro/shadow_private]{.c0}

[./squashfs-root/usr/bin/passwd]{.c0}

[./squashfs-root/usr/sbin/chpasswd]{.c0}

[./squashfs-root/var/etc/passwd]{.c0}

[./squashfs-root/var/etc/passwd_private]{.c0}

[./squashfs-root/var/etc/shadow]{.c0}

[./squashfs-root/var/etc/shadow_private]{.c0}

[]{.c17 .c8 .c22}

[Install and configure buildroot]{.c2}

Go to [buildroot.org]{.c8} and click [Download]{.c8}[. Download and
extract the package.]{.c0}

[cd]{.c8} to the directory you just created. Then run the command [make
menuconfig]{.c8}[.]{.c0}

[![](images/image12.png){style="width: 567.90px; height: 245.71px; margin-left: -86.13px; margin-top: -10.45px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 395.27px; height: 121.20px;"}

Go to [Target options]{.c8} [\> Target Architecture ]{.c8}and select
[MIPS (little endian)]{.c8}[.]{.c0}

Go to [Toolchain \>]{.c8} [Toolchain type]{.c8}[ and switch the C
library to ]{.c18}[musl]{.c8}[.]{.c18}

[![](images/image13.png){style="width: 664.80px; height: 373.73px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 664.80px; height: 373.73px;"}

[![](images/image15.png){style="width: 664.80px; height: 373.73px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 664.80px; height: 373.73px;"}

Select [Exit]{.c8}[ to go back to the main menu.]{.c18}

Go to [Build options ]{.c8}and set [libraries]{.c8} to [shared
only]{.c8}[.]{.c0}

[![](images/image16.png){style="width: 664.80px; height: 373.73px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 664.80px; height: 373.73px;"}

Go back to the main menu and use the left and right arrow keys to select
[Save]{.c8}. Select [OK]{.c8} and press [enter]{.c8}[.]{.c0}

[![](images/image17.png){style="width: 625.19px; height: 354.83px; margin-left: -0.00px; margin-top: -0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 530.40px; height: 308.07px;"}

[![](images/image18.png){style="width: 470.39px; height: 287.26px; margin-left: -70.62px; margin-top: -12.92px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 327.73px; height: 236.67px;"}

Select [Exit]{.c8}[ to close the menuconfig tool.]{.c0}

Next, run the command [make tcpdump]{.c8}[. It will take a while,
possibly 20 minutes or more.]{.c0}

[![](images/image19.png){style="width: 568.64px; height: 346.83px; margin-left: -84.93px; margin-top: -15.65px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);"}]{style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 396.60px; height: 285.33px;"}

[]{.c0}
