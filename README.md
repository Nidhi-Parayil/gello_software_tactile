

To launch the robots 

python scripts/gello_get_offset.py --start-joints 

env: conda activate gello_software_tactile



python experiments/launch_nodes.py --robot xarm
python experiments/run_env.py --agent=gello --use-save-interface


When using the sensor:

start the sensor:
General  instruction for connecting the sensors in any computer (test only on linux):
1. connect the two cables (power and data)
2. activate CAN bus for linux
    - dmesg | grep tty
    - ls /dev/ttyUSB*
    sudo slcand -o -s8 -t hw -S 3000000 /dev/ttyUSB0
    sudo ifconfig slcan0 up

2. run config file from xela_suite_linux folder  ./xela_conf

    ./xela_conf -c slcan0

    sudo ./MoveAroundController/xela_suite_linux/xela_server  -f /etc/xela/xServ.ini


python experiments/launch_nodes.py --robot xarm --use_sensor
python experiments/run_env.py   --agent gello   --gello-port /dev/serial/by-id/usb-FTDI_USB__-__Serial_Converter_FT9HDFUF-if00-port0 --use-save-interface