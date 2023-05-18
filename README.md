# Pixie-Net XL Release Notes


## Version 3.38, April 2022
Release updates include
-	Bug fix in FW for time stamp (high word) for run type 0x411
-	Bug fix in SW for MCA spectra at high rates
-	Bug fix in Igor for extraction of listmode data for channel 3, CFD computation
-	Add new functionality and parameters for trigger distribution 

Known bugs:
- Variant 1: The automatic ADC initialization at boot time sometimes fails. This will be reported as a warning by ./progfippi. To correct, execute ./adcinit manually from the command line.

Note: Version 3.2x of the Zynq controller firmware is compatible with version 3.3x of the processing firmware and software, _except_ for DB08 prototypes

Supported variants are 

| Part Number | Variant ID	| Hardware Revision |	Firmware Revision |	Software Revision |
| ----------- | ----------- | ----------------- | ----------------- | ----------------- |
| Pixie-Net-8-14-500 |7  | DB06, 8  channel, <br/> 14 bit, 500 MSPS, <br/> 10G <br/> Z-Turn Zynq controller | 0x3871 |	[sw-arm-pnxl: 3.39](./release_packages/sw-arm-pnxl-3p39.zip) <br/> [sw-arm-pnxl: 3.38](./release_packages/sw-arm-pnxl-3p38.zip) <br/> [sw-host-pnxl: 09072022](./release_packages/sw-host-pnxl-09072022.zip)<br/> [sw-igor-pnxl: 6.38](./release_packages/sw-igor-pnxl-6p38.zip) <br/> sd-bootfiles-pnxl: ZT-3.25 or ZT-3.32<br/> sd-image-pnxl: 09072022 <br/> [Pixie_Net_XL_Manual: 3.38](./release_packages/Pixie_Net_XL_Manual.pdf) |
| Pixie-Net-16-14-250 | 4	 | DB04, 16  channel, <br/> 14 bit, 250 MSPS, <br/> 10G <br/> Z-Turn Zynq controller <br/> Optional TTCL adapter |	0x3841 |   same as above |
| Pixie-Net-8-14-125 | 1	 | DB01, 8  channel, <br/> 14 bit, 125 MSPS, <br/> 10G <br/> Z-Turn Zynq controller |	0x3811 | same as above |	
| Pixie-Net-16-14-250W | 4W	| DB04, 16  channel, <br/> 14 bit, 250 MSPS, <br/> 1G (White Rabbit) <br/> MicroZed Zynq controller	| 0x2540 <br/> (unchanged from pre-release) |	[sw-arm-pnxl: 3.32](./release_packages/sw-arm-pnxl-3p32.zip) <br/>  [sw-host-pnxl: 09072022](./release_packages/sw-host-pnxl-09072022.zip) <br/>  [sw-igor-pnxl: 6.21](./release_packages/sw-igor-pnxl-6p21.zip) <br/> sd-bootfiles-pnxl: MZ-3.25 <br/>  sd-image-pnxl: 09072022 <br/> [Pixie_Net_XL_Manual: 3.38](./release_packages/Pixie_Net_XL_Manual.pdf) |
 
## Release Information
A full Pixie-Net XL software/firmware release consists of the following components

| Component name | Description	| Install & Update |
| -------------- | ------------ | ----------------- |
| sw-arm-pnxl-[version] | The setup and DAQ procedures that go into /var/www on the Pixie Net XL’s Linux OS (including the binaries for the pulse processing FPGAs). |	Unzip, then copy to /var/www on the Pixie Net XL’s Linux OS |
| sw-host-pnxl-[version] | 	Utilities for the UDP receiver and other DAQ utilities. Includes Igor xop version of UDP receiver |	Unzip, then copy executables to any folder on UDP receiver PC.  <br/> Igor extension udp_xop64.xop must be copied to C:\Program Files\WaveMetrics\Igor Pro 8 Folder\Igor Extensions (64-bit) or equivalent for Igor GUI |
| sw-igor-pnxl-[version]	| Igor GUI for setup, data acquisition, and data visualization via serial port or network. |	First install Igor Pro 8 or higher. <br/> Then unzip and copy to any folder on a Windows PC. |
| sd-bootfiles-pnxl-[version]	| The Zynq controller bootfiles for the FAT partition of the SD card. |	Unzip, then copy the 4 bootfiles to the FAT partition of the SD card
| sd-image-pnxl-[version] | The full (zip compressed) SD card image, includes sw-arm-pnxl, sd-bootfiles-pnxl, and all Linux OS files Only updated for changes in Linux OS |	Unzip, then write to an SD card with a byte-by-byte image writer |
| Pixie_Net_XL_Manual.pdf | The user manual. It is also included in sw-arm-pnxl. | please read |

For first time users, please also see the [Quick Start guide](./release_packages/PixieNetXL_QuickStart.pdf)

## Older Releases 

## Version 3.32, November 2022
Release updates include
-	Debugged and tested CFD in variant 4W

Known bugs:
- Variant 1: The automatic ADC initialization at boot time sometimes fails. This will be reported as a warning by ./progfippi. To correct, execute ./adcinit manually from the command line.  

Supported variants are 

| Part Number | Variant ID	| Hardware Revision |	Firmware Revision |	Software Revision |
| ----------- | ----------- | ----------------- | ----------------- | ----------------- |
| Pixie-Net-8-14-500 |7  | DB06, 8  channel, <br/> 14 bit, 500 MSPS, <br/> 10G <br/> Z-Turn Zynq controller | 0x3171 |	[sw-arm-pnxl: 3.32](./release_packages/sw-arm-pnxl-3p32.zip) <br/> [sw-host-pnxl: 09072022](./release_packages/sw-host-pnxl-09072022.zip)<br/> [sw-igor-pnxl: 6.21](./release_packages/sw-igor-pnxl-6p21.zip) <br/> sd-bootfiles-pnxl: ZT-3.25 <br/> sd-image-pnxl: 09072022 <br/> [Pixie_Net_XL_Manual: 3.32](./release_packages/Pixie_Net_XL_Manual.pdf) |
| Pixie-Net-16-14-250 | 4	 | DB04, 16  channel, <br/> 14 bit, 250 MSPS, <br/> 10G <br/> Z-Turn Zynq controller <br/> Optional TTCL adapter |	0x3141 |   -"- |
| Pixie-Net-8-14-125 | 1	 | DB01, 8  channel, <br/> 14 bit, 125 MSPS, <br/> 10G <br/> Z-Turn Zynq controller |	0x3111 | -"- |	
| Pixie-Net-16-14-250W | 4W	| DB04, 16  channel, <br/> 14 bit, 250 MSPS, <br/> 1G (White Rabbit) <br/> MicroZed Zynq controller	| 0x2540 <br/> (unchanged from pre-release) |	[sw-arm-pnxl: 3.32](./release_packages/sw-arm-pnxl-3p32.zip) <br/>  [sw-host-pnxl: 09072022](./release_packages/sw-host-pnxl-09072022.zip) <br/>  [sw-igor-pnxl: 6.21](./release_packages/sw-igor-pnxl-6p21.zip) <br/> sd-bootfiles-pnxl: MZ-3.25 <br/>  sd-image-pnxl: 09072022 <br/> [Pixie_Net_XL_Manual: 3.32](./release_packages/Pixie_Net_XL_Manual.pdf) |
 

## Version 3.31, October 2022
Release updates include
-	Debugged and tested CFD in variant 4
-	Updated TTCL interface for variant 1,4,7 (still preliminary)
-	Updated Igor list mode data displays and tables

Known bugs:
- Variant 1: The automatic ADC initialization at boot time sometimes fails. This will be reported as a warning by ./progfippi. To correct, execute ./adcinit manually from the command line.  

Supported variants are 

| Variant ID	| Hardware Revision |	Firmware Revision |	Software Revision |
| ----------- | ----------------- | ----------------- | ----------------- |
| 7  | DB06, 8  channel, <br/> 14 bit, 500 MSPS, <br/> 10G <br/> Z-Turn Zynq controller | 0x3171 |	[sw-arm-pnxl: 3.31](./release_packages/sw-arm-pnxl-3p31.zip) <br/> [sw-host-pnxl: 09072022](./release_packages/sw-host-pnxl-09072022.zip) <br/> sw-igor-pnxl: 6.21 <br/> sd-bootfiles-pnxl: ZT-3.25 <br/> sd-image-pnxl: 09072022 |
| 4	 | DB04, 16  channel, <br/> 14 bit, 250 MSPS, <br/> 10G <br/> Z-Turn Zynq controller <br/> Optional TTCL adapter |	0x3141 |   -"- |
| 1	 | DB01, 8  channel, <br/> 14 bit, 125 MSPS, <br/> 10G <br/> Z-Turn Zynq controller |	0x3111 | -"- |	
| 4W	| DB04, 16  channel, <br/> 14 bit, 250 MSPS, <br/> 1G (White Rabbit) <br/> MicroZed Zynq controller	| 0x2540 <br/> (unchanged from pre-release) |	sw-arm-pnxl: 3.31 <br/>  [sw-host-pnxl: 09072022](./release_packages/sw-host-pnxl-09072022.zip) <br/>  sw-igor-pnxl: 6.21 <br/> sd-bootfiles-pnxl: MZ-3.25 <br/>  sd-image-pnxl: 09072022 |
 

### Version 3.30, September 2022
First commercial release. Supported variants are 

| Variant ID	| Hardware Revision |	Firmware Revision |	Software Revision |
| ----------- | ----------------- | ----------------- | ----------------- |
| 7  | DB06, 8  channel, <br/> 14 bit, 500 MSPS, <br/> 10G <br/> Z-Turn Zynq controller | 0x3071 |	sw-arm-pnxl: 3.30 <br/> sw-host-pnxl: 09072022 <br/> sw-igor-pnxl: 6.20 <br/> sd-bootfiles-pnxl: ZT-3.25 <br/> sd-image-pnxl: 09072022 |
| 4	 | DB04, 16  channel, <br/> 14 bit, 250 MSPS, <br/> 10G <br/> Z-Turn Zynq controller <br/> Optional TTCL adapter |	0x3041 |   -"- |
| 1	 | DB01, 8  channel, <br/> 14 bit, 125 MSPS, <br/> 10G <br/> Z-Turn Zynq controller |	0x3011 | -"- |	
| 4W	| DB04, 16  channel, <br/> 14 bit, 250 MSPS, <br/> 1G (White Rabbit) <br/> MicroZed Zynq controller	| 0x2540 <br/> (unchanged from pre-release) |	sw-arm-pnxl: 3.30 <br/>  sw-host-pnxl: 09072022 <br/>  sw-igor-pnxl: 6.20 <br/> sd-bootfiles-pnxl: MZ-3.25 <br/>  sd-image-pnxl: 09072022 |
