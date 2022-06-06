# slip-serial-to-network

Used for forwarding OSC packets sent from Arduino through SLIPSerial to programs that expect the packets to come from the network.

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
