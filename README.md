<h1 align="center">
  <br>
    <a>SERBERUS</a>
</h1>

<h4 align="center">Multi-headed and Multi-Protocol embedded system hacking tool.</h4>

---

Serberus is a FT42xx based 4 port USB to serial tool for testing and talking to embedded systems.

<p align="center">
  <img alt="Serberus Board" title="Serberus Board" width="500px" src="Serberus_Proto.jpeg">
  <br>
</p>
The Serberus is a serial Man-in-the-Middle hardware hacking tool designed to connect to embedded devices . It has 4 channels and has headers to interface with up to 3 UARTs simultaneously and also has the ability to connect to JTAG, SPI, I2C and SWD interfaces. During this talk I will introduce the Serberus and what makes it different than other, similar tools.  It has a level shifter and switch  to allow you to connect to logic voltages of 1.8, 2.5 and 3.3v or any arbitrary voltage between 1.65v and 5.5v, matching that of your target. The Serberus is unique in that it was designed to use open source tools like the [Akheron proxy](https://github.com/rapid7/akheron-proxy) in order to MitM serial communications
The Serberus is an FT4233 based USB to serial device designed for embedded system penetration testing. It is designed to be compatible with several libraries that already support the FTDI x23x series of interfaces including OpenOCD. Any serial console that can connect to an FTDI based usb to serial port should be able to use this tool. When connected to a computer it presents as 4 serial ports. The first port is UART, the second is the multi-purpose JTAG, SWD, I2C and SPI port, as well as the port used for programming. Serial ports 3 and 4 are also UART.
<br>
The Serberus has two 20-pin bus connectors, one for all 3 UARTs and the other that is designed to be pin compatible with the 20 pin Segger J-link. There are a number of adapters for the J-link that should work directly with the Serberus. The board has separate TX and RX indicators for each channel as well, using a clever feature built into the FTDI that allows the serial EEPROM signals to feed a Nexperia shift register. 
<br>
The Serberus also has a 14 pin 2.54mm pitch connector to attach a logic analyzer. I use a Salae in my workflow and with this pitch you can use normal size Dupont style jumper wires or the Salae connector to directly interface with the TX and RX pins of each channel. The board also has a 10 pin mini cortex connector, an 8 pin SPI and 4 pin I2C connector.
I am releasing all of the designs and files used to build and design this tool as open source, under the Apache 2.0 license. That was also the license carried over from the TIMEP. 
There are many tools out there that use the FT based USB to serial converters for this type of testing. The closest examples are the TIMEP and TIGARD, both of which use a similar level shifter design. 
<br>
## What makes the Serberus unique is the following:
This is the first unit with multiple UART ports, allowing for MitM testing using tools such as the Akheron proxy (https://github.com/rapid7/akheron-proxy).
This unit uses a not very well documented feature in the FT 423x processors that allow for 8 serial channel TX and RX indicators to be driven from the serial EEPROM signal lines. This allows the tester to see what each channel is doing when verifying connectivity.
J-Link compatible JTAG connector, the same pinout that is used by the J-link, this allows the Serberus to use the many J-link interface boards to allow for easy connection to needle adapters, cortex programming headers that use the fine pitched headers and other adapters that use this pinout. This allows a tester to easily interface with a larger number of devices that use this pinouts on their production systems.
2.54 mm Logic header, this header allows for easy connection to a logic analyzer using dupont wires or an MSO oscilloscope’s logic probes. 

## How do I get one? Please be patient, more information coming soon, in the meantime, please feel free to grab the designs and make your own.
