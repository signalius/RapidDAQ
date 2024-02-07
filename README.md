
## RapidDAQ

RapidDAQ is a completely open source Data Aquistion Platform that includes few extraordinary features. 

![Pcb](https://raw.githubusercontent.com/signalius/RapidDAQ/main/doc/rapiddaq_pcb3d.png)

### Analog input specification

 * ADC: 3 ch, 80MSps, 12 bits 
 * 1 x 1 MOhm 40MSps analog input with standard BNC connector
 * 1 x 50 ohm 40MSps analog input with SMA connector
 * 1 x Piezo 20MSps input with SMA connector

The maximum sampling speed of the ADC is 80MSps using a single channel. All analogue inputs can operate simultaneously, but at reduced speed.

### Digital input specification

 * 8 x general input/output ports
 * Compatible with 3.3V or 5 V
 * Can be mapped as SPI, UART or special Timer in/out.


### Interface

 * USB C HS 480Msps
 * I2C port
 * SPI (using GPIO pins)
 * UART (using GPIO pins)

### OS compatibility

 * RapsberryPI (tested on version 4 and 5)
 * Linux (tested on Ubuntu 22.04)
 * Windows 
 * MacOS (not tested)
 
The library uses libusb for communication, so any system that have this library should be compatible. 

## Why is RapidDAQ not a HAT for the RaspberryPI?

The USB HS interface, which offers data transfer rates as high as 480 Mbps, enables fast data exchange and does not occupy our expansion slots so the RaspberryPi can be used in parallel with other extensions. The Raspberry Pi has up to 4 USB slots so we can connect up to 4 RapidDAQ devices. The use of USB also assures us that RapidDaq can be used without any modifications with other devices including a PC (Linux and Windows operating systems have been tested).

## What is the difference between DAQ and Scope?

The oscilloscope has a trigger and only collects data when triggered until the internal memory is full. This data is then shown on the screen or transferred to a PC usually much slower than the oscilloscope allows it to collect. An oscilloscope is therefore not suitable for applications where we need to record or process an analogue signal continuously in real time. This is where the DAQ comes to the rescue, enabling continuous data collection and real-time transfer of this data to an RaspberryPi or PC for processing or storage. This means that a DAQ can work like an oscilloscope but an oscilloscope cannot work like a DAQ.

## License
RapidDAQ is fully open source.

All software, hardware and documentation unless otherwise noted, is licensed under CC BY-SA 4.0.

The host software is derived from the brilliantly written HackRF source code, as my intention was to maintain compatibility with the Gnu Radio project. [HackRF github repo](https://github.com/greatscottgadgets/hackrf/)

## Website
[Manual and store](https://gepard.space/)


