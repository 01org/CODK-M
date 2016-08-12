# Curie Open Development Kit - M

### Contents

  - Firmware: Zephyr (x86 core)
  - Software: Arduino sketches or `*.cpp` (ARC core)

### Supported Platforms
 - Ubuntu 14.04 - 64 bit

### Installation
```
mkdir CODK && cd $_
git clone https://github.com/01org/CODK-M.git
cd CODK-M
make clone
sudo make install-dep
make setup
source ../zephyr/zephyr-env.sh
```

### Compile
- Firmware: `make compile-firmware`
- Software: `make compile-software`
- Both: `make compile`

### Upload

##### Using USB/DFU
- Firmware: `make upload-firmware-dfu`
- Software: `make upload-software-dfu`
- Both: `make upload`

##### Using JTAG
- Firmware: `make upload-firmware-jtag`
- Software: `make upload-software-jtag`
- Both: `make upload-jtag`

Default app blinks the pin-13 LED on Arduino 101 board

### Debug
Connect JTAG and open three terminal tabs

##### Tab 1: Debug Server
`make debug-server`

##### Tab 2: Firmware
`make debug-firmware`    
`(gdb) target remote localhost:3334`

##### Tab 3: Software
`make debug-software`    
`(gdb) target remote localhost:3333`
