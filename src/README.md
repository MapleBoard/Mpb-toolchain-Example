This file shows how to use the Makefile to build the executable file for gd32vf103 development board from source.

We recommand using our prebuild toolchain, download link is here:  

also, you can build the riscv-gnu-toolchain from scratch (provided by nuceli), download link is here:https://github.com/riscv-mcu/riscv-gnu-toolchain  

If you replace our MapleBoard toolchain into your own toolchain, remember to modify the $(PREFIX) variable at line 54 of Makefile, like this  

<pre><code>
PREFIX = riscv32-unknown-elf-
</code></pre>

Goodluck!

The make instruction has serval option:
* make		: make .elf .hex and .bin files in binary to upload to GD32 RISC-V Nano/Pico.
* make clean 	: clean up the files that generated by the building process and result.
* make flash	: use openocd command to flash program into memory 
* make dfu	: use dfu-util to upload the firmware to GD32 RISC-V Nano/Pico
* make uart	: use stm32flash command to upload the binary firmware file

The dfu-util should be the newest (2020-08-10) otherwisw, the utility will show you upload success but the board still not working.  

You can download the source code [HERE](https://sourceforge.net/p/dfu-util/dfu-util/ci/master/tree/)
and follow the README guide to install.
