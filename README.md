# OneInchEye: OpenSource IMX283 Camera Board for Raspberry Pi
![](https://imgur.com/olbFNfe.jpg)

### Update on 2024/03/24
This project is also compatiable with RPI5, the quickstart guide has been updated.  

Currently an known issue is that the camera mode transition from 2K -> 5K(mode 0) will causes camera not sending the correct frame, the workaround is to use `--viewfinder-mode 5568:3664:12:P --mode 5568:3664:12:P` to ask the rpicam-jpeg to use the full res mode for AWB and AutoExposure.  

## Introduction
Welcome to the **OneInchEye** project, an open-source camera board designed for Raspberry Pi Compute Module 4 boards using the IMX283 one-inch sensor. This project aims to provide a high-quality, affordable, and accessible camera module for advanced Raspberry Pi projects. The board is designed using KiCad v6, a popular open-source electronics design automation (EDA) software.

OneInchEye captures stunning high-resolution images and videos with improved low-light performance and dynamic range. It's perfect for photography enthusiasts, developers, and makers who want to level up their Raspberry Pi projects with a powerful camera. The board also features a TMP117 temperature sensor for accurate temperature readings.

**Please note that the OneInchEye is not compatible with most Raspberry Pi boards because it requires 22-pin FPC connector with 4-lane MIPI-CSI interface. Ensure compatibility with your specific board before proceeding.**

## Features
* 1-inch IMX283 sensor
* **Open-source hardware and software**
* Integrated TMP117 temperature sensor
* Compatible with Raspberry Pi Compute Module 4 boards with a 22-pin FPC connector and 4-lane MIPI-CSI (same pinout as Raspberry Pi Compute Module 4 IO Board)

## Support
For questions, issues, or suggestions, please open an issue in the [GitHub repository](https://github.com/will127534/OneInchEye/issues)  
Also see [Quick Start Guide](https://github.com/will127534/OneInchEye/wiki/OneInchEye-Quick-Start-Guide)


## MISC stuff  
1. Blog post(?) here: https://will127534.github.io/OneInchEye/
1. I know the decoupling capacitors in sch are a mess.....  
2. TMP117 temperature sensor is hook up at the 1.8V LDO for cleaner power, but that LDO is controlled by CAM_GPIO (or think as a enable pin for the camera module), so it will function only when the camera is active.  
3. There is no clock sync function for the CMOS sensor, so the XVS and XHS are output only.  
4. QWIIC is mainly for hooking up to other I2C devices so you don't have to connect yet another cable if you add additional I2C sensor to the board. But it also serves as I2C debug port to hook up external logic analyzer.  
5. This board is actually quite easy to assemble, if you want to build board yourself, you can use JLCPCB to do the PCBA on component side and do the CMOS side with low temperature soldering paste yourself if you can source the CMOS sensor. The JLCPCB BOM and Position list is also provided.
6. Limited quantity on Tindle: https://www.tindie.com/products/will123321/oneincheye/

## License
This project is released under the MIT License.
![](https://i.imgur.com/5n1qKnF.png)
![](https://i.imgur.com/auB4iKB.png)


Thanks to ChatGPT helping me generating most of the Readme, see if you can spot which section I typed.
