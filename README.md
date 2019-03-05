# nibe2mqtt

1. Enter sudo raspi-config in a terminal window
2. Select Interfacing Options
3. Navigate to and select Serial
4. Choose No (Login shell over serial)
5. Choose Yes (Enable serial hardware)
6. Choose OK
7. Choose Finish
8. Reboot

1. Install git "sudo apt-get update && sudo apt-get install git"
2. Clone this repository "git clone https://github.com/bebben88/nibe2mqtt"

# Install Node-RED
```bash <(curl -sL https://raw.githubusercontent.com/node-red/raspbian-deb-package/master/resources/update-nodejs-and-nodered)```
Make it autostart on boot
```sudo systemctl enable nodered.service```
Start Node-RED
```sudo systemctl start nodered.service```
Import the flow from the file nodered.flows
Now you can Deploy.
# Start NibeGW script
open folder "cd nibe2mqtt"
Build the nibegw.c script with the command "gcc -std=gnu99 -o nibegw nibegw.c"

./nibegw -h

    -h                 Print help
    -v                 Print debug information
    -d <device name>   Serial port device (default: /dev/ttyS0)
    -a <address>       Remote host address (default: 127.0.0.1)
    -p <port>          Remote UDP port (default: 9999)
    -f                 Disable flow control (default: HW)
    -r <address>       RS-485 address to listen (default: 0x20)
    -i                 Send all messages by UDP (default: only modbus data)
    -n                 Don't send acknowledge at all
    -o                 Send acknowledge to all addresses
    -t                 Test mode
    -l <port>          Local UDP port for read commands (default: 9999)
    -w <port>          Local UDP port for write commands (default: 10000)
    -q                 Print data in log format
    
run example:

  ./nibegw -v -d /dev/serial0
