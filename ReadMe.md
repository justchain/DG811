This  firmware can change your RIGOL DG8xx generator and DG9xx to DG992, it can output up to 100 Mhz, but the DG811 has a maximum output of 10MHZ and only one channel is available,  and the only good thing about it is that it's cheap. The software and hardware of DG811 and DG992 are the same,so I use IDA to decompile the DG8's firmware and find a method whitch can change my DG811 to DG992.

1.You have to prepare an Arduino Uno R3 and some new MB85RC16, and use some Arduino Firmware Burning Tools(https://github.com/uname/Arduloader) to flash this firmware in your Arduino.

2.Disassemble your DG811 or other model.

3.Find EEPROM with 'RC16'(Fujitsu MB85RC16) code on the AM3352 core board and take it down. Before rewriting the data in it, you should write a program to backup the data of EEPROM , this program is very easy, so I won't give it to you.

4.Connect EEPROM to Arduino used I2C bus, WP pin is  NC, and you can refer https://github.com/sosandroid/FRAM_MB85RC_I2C , I use this library to driver MB85RC16.

5.Make sure the connection is correct, power on it, wait the arduino console print the model string like as 'DG811' and 'Finished,please enjoy your DG992......'. That means success.

6.Welding EEPROM to core board.

End!

