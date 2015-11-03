---
published: true
layout: default
title: build micropython on STM32F4 Discovery Board
---
<p class="publish_date"> 2015.06.19</p>


<img src="{{ site.baseurl }}/images/stm32f4.jpg" alt="Drawing" style="width: 400px;"/>


[micropython](http://micropython.org/)-ыг [kickstarter](https://www.kickstarter.com/projects/214379695/micro-python-python-for-microcontrollers?lang=de)-д гарснаас хойш хөгжүүлэлтийг нь 6 сар тасралтгүй ажиглаж байна. өөрт байсан STM32F4 Discovery Board-д micropython-г туршсан байдлаа доор харуулья. **MacOs** үйлдлын системыг ашиглав. линукстэй төстэй учир бараг бүх явц адилхан.

mikropython-ыг хөрвүүлхэд [arm-none-eabi-gcc](https://launchpad.net/gcc-arm-embedded/+download) compiler хэрэгтэй болно. үүнийг [эндээс](https://launchpad.net/gcc-arm-embedded/+download) татаж авья.

хаана хадгалснаас хамаар ч дараах байдлаар **.bashrc**-д юм уу **.bash_profile**-д байрлуулья.

<pre class="terminal" name="code">
export PATH=/Volumes/work/gcc_arm_versions/gcc-arm-none-eabi/bin:$PATH
</pre>

дараа нь **source .bash_profile** эсвэл **source .bashrc** комманд-р терминалаас arm-gcc-compiler-ыг дуудах боломжой болно.

micropython-ыг эх кодыг дараах байдлаар **Downloads** хавтасд татья.

<pre class="terminal" name="code">
cd ~/Downloads/
git clone https://github.com/micropython/micropython.git
</pre>

татаж авсан хойноо **micropython/stmhal** хавтасруу орно. 

**make** **BOARD=STM32F4DISC** коммандаар микроконтролерт байрлуулах үйлдлын системыг хөрвүүлье.


<pre class="terminal" name="code">
cd ~/Downloads/micropython/stmhal
make BOARD=STM32F4DISC
</pre>


ойролцоогоор 1 минут орчим хөрвүүлж уншисан хойно дараах файлууд үүснэ. 

<pre class="terminal" name="code">
LINK build-STM32F4DISC/firmware.elf
   text	   data	    bss	    dec	    hex	filename
 265640	     96	  27664	 293400	  47a18	build-STM32F4DISC/firmware.elf
Create build-STM32F4DISC/firmware.dfu
Create build-STM32F4DISC/firmware.hex 
</pre>


үүсгэсэн үйлдлын системийг виртуал com port холболтоор микроконтроллерт татаж байршуулaxын тулд STM32F4 Board -ын bootloader-ыг **BOOT0** pin-г **VDD** холбон  **RESET** товчыг дарснаар идэвхжүүлнэ. дараах зураг дээрээс тодорхой харагдана.

<img src="{{ site.baseurl }}/images/boot0.jpg" alt="Drawing" style="width: 300px;"/>

microusb кабелаар виртуал com port холболт үүснэ. дан ганцаараа хавтанг цахилгаанаар хангаж чадахгүй учир miniusb кабелыг компютерт залгах болсон.

өмнө үүсгэсэн үйлдлын системыг микроконтроллерт байрлуулхад **dfu-util** программ хэрэг болно. 

<pre class="terminal" name="code">
brew install dfu-util minicom
</pre>

линукс ашиглаж байгаа хүмүүс дараах байдлаар суулгана.

<pre class="terminal" name="code">
sudo apt-get install dfu-util
</pre>

ликукстэй хүмүүс **sudo** **vi** **/etc/udev/rules.d/49-stmdiscovery.rules** файл үүсгэн энэ өгөгдлийг хадаглана.

<pre class="terminal" name="code">
sudo vi /etc/udev/rules.d/49-stmdiscovery.rules
</pre>


<pre class="terminal" name="code">
# f055:9800 - STM32F4 Discovery running MicroPython in USB Serial Mode (CN5)
ATTRS{idVendor}=="f055", ATTRS{idProduct}=="9800", ENV{ID_MM_DEVICE_IGNORE}="1"
ATTRS{idVendor}=="f055", ATTRS{idProduct}=="9800", ENV{MTP_NO_PROBE}="1"
SUBSYSTEMS=="usb", ATTRS{idVendor}=="f055", ATTRS{idProduct}=="9800", MODE:="0666"
KERNEL=="ttyACM*", ATTRS{idVendor}=="f055", ATTRS{idProduct}=="9800", MODE:="0666"
# 0483:df11 - STM32F4 Discovery in DFU mode (CN5)
SUBSYSTEMS=="usb", ATTRS{idVendor}=="0483", ATTRS{idProduct}=="df11", MODE:="0666"
</pre>


ликукстэй хүмүүс sudo udevadm control --reload-rules коммандаар өмнө үүсгэсэн файлыг ликукс системд дараах байдлаар уншуулна.

<pre class="terminal" name="code">
sudo udevadm control --reload-rules
</pre>

үүсгэсэн үйлдлын ситемыг дараах байдлаар микроконтроллерт татья.

<pre class="terminal" name="code">
sudo make BOARD=STM32F4DISC deploy
Password:
Use make V=1 or set BUILD_VERBOSE in your environment to increase build verbosity.
Writing build-STM32F4DISC/firmware.dfu to the board
dfu-util 0.8

Copyright 2005-2009 Weston Schmidt, Harald Welte and OpenMoko Inc.
Copyright 2010-2014 Tormod Volden and Stefan Schmidt
This program is Free Software and has ABSOLUTELY NO WARRANTY
Please report bugs to dfu-util@lists.gnumonks.org

Opening DFU capable USB device...
ID 0483:df11
Run-time device DFU version 011a
Claiming USB DFU Interface...
Setting Alternate Setting #0 ...
Determining device status: state = dfuERROR, status = 10
dfuERROR, clearing status
Determining device status: state = dfuIDLE, status = 0
dfuIDLE, continuing
DFU mode device DFU version 011a
Device returned transfer size 2048
DfuSe interface name: "Internal Flash  "
file contains 1 DFU images
parsing DFU image 1
image for alternate setting 0, (2 elements, total size = 265752)
parsing element 1, address = 0x08000000, size = 10380
Download	[=========================] 100%        10380 bytes
Download done.
parsing element 2, address = 0x08020000, size = 255356
Download	[=========================] 100%       255356 bytes
Download done.
done parsing DfuSe file 
</pre>


<pre class="terminal" name="code">
dfu-util -a 0 -d 0483:df11 -D build-STM32F4DISC/firmware.dfu
dfu-util 0.8

Copyright 2005-2009 Weston Schmidt, Harald Welte and OpenMoko Inc.
Copyright 2010-2014 Tormod Volden and Stefan Schmidt
This program is Free Software and has ABSOLUTELY NO WARRANTY
Please report bugs to dfu-util@lists.gnumonks.org

Opening DFU capable USB device...
ID 0483:df11
Run-time device DFU version 011a
Claiming USB DFU Interface...
Setting Alternate Setting #0 ...
Determining device status: state = dfuIDLE, status = 0
dfuIDLE, continuing
DFU mode device DFU version 011a
Device returned transfer size 2048
DfuSe interface name: "Internal Flash  "
file contains 1 DFU images
parsing DFU image 1
image for alternate setting 0, (2 elements, total size = 265752)
parsing element 1, address = 0x08000000, size = 10380
Download	[=========================] 100%        10380 bytes
Download done.
parsing element 2, address = 0x08020000, size = 255356
Download	[=========================] 100%       255356 bytes
Download done.
done parsing DfuSe file
</pre>


одоо туршиж үзхэд бэлэн боллоо. 

<pre class="terminal" name="code">
minicom -D /dev/tty.usbmodem*
</pre>

эсвэл

<pre class="terminal" name="code">
screen /dev/tty.usbmodem*
</pre>

