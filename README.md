# Pcapped
An implementation of Gopackets library.

##Requirements
```
go get github.com/google/gopackets
go get github.com/google/gopacket/layers
go get github.com/google/gopacket/pcap
```

Automatic installation:
```sh
go mod download
```

Make sure you have installed libpcap.Gopackets is built on top of it.
 ```bash
 sudo apt-get install libpcap-dev
 ```

Check all devices by running the checkdevices.go file as root :
```bash
sudo go run checkdevices.go
```

The output is like this:
```sh
Devices found:

Name:  usb0
Description:  
Devices addresses:  
- IP address:  192.168.42.110
- Subnet mask:  ffffff00
- IP address:  fe80::701f:d5a2:923e:9661
- Subnet mask:  ffffffffffffffff0000000000000000

Name:  lo
Description:  
Devices addresses:  
- IP address:  127.0.0.1
- Subnet mask:  ff000000
- IP address:  ::1
- Subnet mask:  ffffffffffffffffffffffffffffffff

Name:  any
Description:  Pseudo-device that captures on all interfaces
Devices addresses:  Pseudo-device that captures on all interfaces

Name:  eth0
Description:  
Devices addresses:  

Name:  docker0
Description:  
Devices addresses:  
- IP address:  172.17.0.1
- Subnet mask:  ffff0000

Name:  bluetooth-monitor
Description:  Bluetooth Linux Monitor
Devices addresses:  Bluetooth Linux Monitor

Name:  nflog
Description:  Linux netfilter log (NFLOG) interface
Devices addresses:  Linux netfilter log (NFLOG) interface

Name:  nfqueue
Description:  Linux netfilter queue (NFQUEUE) interface
Devices addresses:  Linux netfilter queue (NFQUEUE) interface

Name:  dbus-system
Description:  D-Bus system bus
Devices addresses:  D-Bus system bus

Name:  dbus-session
Description:  D-Bus session bus
Devices addresses:  D-Bus session bus

Name:  bluetooth0
Description:  Bluetooth adapter number 0
Devices addresses:  Bluetooth adapter number 0
```

In my case, I was using usb-tethering, so my active device is *usb0*
Set in as the open device in the main.go file,line 15.

###Open live capture
Run the main.go file as root:
```bash
sudo go run main.go
``` 

...and see awesomeness!

Have fun! 