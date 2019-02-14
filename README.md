# pynq-boards
Board files to build a PYNQ image

## Currently Supported Boards

| Board Name  | Last Tested PYNQ Version | Link to BSP |
| ----------- | ------------------------ | ----------- |
| ZedBoard | Master - c2d606 | [2018.2](https://www.xilinx.com/member/forms/download/xef.html?filename=avnet-digilent-zedboard-v2018.2-final.bsp), [2018.3](https://www.xilinx.com/member/forms/download/xef.html?filename=avnet-digilent-zedboard-v2018.3-final.bsp) |

## Requirements

You should read [pynq_sd_card](https://pynq.readthedocs.io/en/v2.3/pynq_sd_card.html):
- Ubuntu 16.04 LTS 64-bit (in a Virtual Machine)
- passwordless sudo
- Xilinx Vivado and PetaLinux (same version as BSP needed)

You also need a Xilinx Account for the BSP.

## Quick Start

Clone PYNQ: 
```
git clone https://github.com/Xilinx/PYNQ.git
```

Install dependencies:
``` 
<PYNQ repository>/sdbuild/scripts/setup_host.sh
```

Clone this git ***outside*** the PYNQ directory: 
```
git clone https://github.com/cklarhorst/pynq-boards.git
```

Download and copy the BSP Package into your board directory.

Build the image:
```
cd <PATH TO PYNQ>/sdbuild
make BOARDDIR="<PATH TO pynq-boards>" BOARDS="<YOUR BOARD>"
```
SD card image will be placed in the `PYNQ/sdbuild/` directory.
