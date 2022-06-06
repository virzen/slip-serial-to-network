# slip-serial-to-network

A simple Node.js script that acts as a bridge between
an Arduino or Teensy that uses the OSC (Open Sounc Control)
protocol over SLIP (Serial Line Internet Protocol)
and a program that uses the OSC protocol over UDP.

Setup:
```shell
npm install
```

Usage:
```shell
npm start [-- COM-port [local-port [remote-port [remote-address]]]]
```

The port to set the external program (MapMapper, Reaper) to is the `remote-port`.

The script will automatically look for Arduino or Teensy boards connected
via USB. If no such board can be find, the first COM port will be selected and 
a list of found ports will be shown for inspection.
You can specify a port to override the search for Arduinos.

If no ports are specified, port 8888 is used for local send/receive port
and 9999 for remote receive port. The default remote address is 'localhost'.

If a local port is specified, but no remote port or address, 
port 9999 is used as the remote port, and the default remote address is 'localhost'.

If a local port and a remote port are specified, but no remote address,
'localhost' is used as remote address.

When a UDP message on the local port is received, the remote address will
be automatically updated to the sender of that UDP message. The remote port
will not be altered.

The local port corresponds to the 'send' port in the audio software.
The remote port corresponds to the 'receive' port in the audio software.

## Credits

Based on [ttapa/Projects/NodeJS/SLIP](https://github.com/tttapa/Projects/tree/master/Arduino/NodeJS/SLIP) and [thread on Arduino forum](https://forum.arduino.cc/t/osc-over-usb/520680), thanks a lot!
