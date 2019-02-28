# nibe2mqtt

Clone the repository.

Build the nibegw.c script with the command "gcc -std=gnu99 -o nibegw nibegw.c"

nibegw -h

./nibegw usage:

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

  ./nibegw -v -d /dev/ttyUSB0 -a 192.168.1.10
