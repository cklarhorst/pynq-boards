# pynq-boards
Board files to build a PYNQ image

## Currently Supported Boards

| Board Name  | Last Tested PYNQ Version | Link to BSP | What was tested |
| ----------- | ------------------------ | ----------- | --------------- |
| ZedBoard | Master - c2d606 | [2018.2](https://www.xilinx.com/member/forms/download/xef.html?filename=avnet-digilent-zedboard-v2018.2-final.bsp), [2018.3 (not tested yet)](https://www.xilinx.com/member/forms/download/xef.html?filename=avnet-digilent-zedboard-v2018.3-final.bsp) | [TVM/VTA](https://github.com/dmlc/tvm), [BNN-PYNQ](https://github.com/Xilinx/BNN-PYNQ), [QNN-MO-PYNQ](https://github.com/Xilinx/QNN-MO-PYNQ)|

## Requirements

You should read [pynq_sd_card](https://pynq.readthedocs.io/en/v2.3/pynq_sd_card.html):
- Ubuntu 16.04 LTS 64-bit (in a Virtual Machine)
- passwordless sudo
- Xilinx Vivado, SDx and PetaLinux (same version as BSP needed)

You also need a Xilinx Account for the BSP.

## Quick Start

1. Clone PYNQ: 
```
git clone https://github.com/Xilinx/PYNQ.git
```

2. Install dependencies:
``` 
<PYNQ repository>/sdbuild/scripts/setup_host.sh
```

3. Clone this git ***outside*** the PYNQ directory: 
```
git clone https://github.com/cklarhorst/pynq-boards.git
```

4. Download and copy the BSP Package into your board directory.

5. Update the BSP entry in your spec file under `<PATH TO pynq-boards>/<YOUR BOARD>/<YOUR BOARD>.spec` according to your BSP version

6. Build the image:
```
cd <PATH TO PYNQ>/sdbuild
make BOARDDIR="<PATH TO pynq-boards>" BOARDS="<YOUR BOARD>"
```

If you encounter an error like:
```
which vivado | fgrep 2018.2
Makefile:307: recipe for target 'checkenv' failed
```
You have to execute:
```
source /tools/Xilinx/Vivado/2018.2/settings64.sh
```

SD card image will be placed in the `PYNQ/sdbuild/` directory.
