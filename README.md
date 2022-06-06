# slip-serial-to-network

Created for forwarding OSC packets sent from Arduino through SLIPSerial to programs that expect the packets to come from the network, specifically for MadMapper, might work for other ones.

## Running
```shell
npm start
```

## Port config
Arduino is assumed to be on COM4, if it's different change the assignment to `path` variable in the code. 

You can look it up in the hardware manager, but there is also some detection capability. If you comment out the `path = 'COM4'` line, the program will try to detect the port Arduino is connected on. It usually fails, but it will give you a list of devices and you might notice Arduino in there.

```js
path = 'COM1'
```

## Credits

Based on [ttapa/Projects/NodeJS/SLIP](https://github.com/tttapa/Projects/tree/master/Arduino/NodeJS/SLIP) and [thread he sent it over](https://forum.arduino.cc/t/osc-over-usb/520680), thanks a lot!
