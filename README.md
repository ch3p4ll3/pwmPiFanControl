# RPiFanControl
With this simple script you can control the speed of a fan according to the cpu temperature of your Raspberry. By default I use pin 13 (BCM), the fan will start to turn on when the Raspberry is at 25 ° C to reach the maximum speed when the temperature rises to 65 ° C. The fan I used is that of an old 12V PC fan, follow the circuit below for the connections

## Wirings

![wirings](https://i.stack.imgur.com/rSeVt.png)

## How to install
**Note:** To use the program you must have installed the pigpio daemon. To install it type `sudo apt install pigpiod`. The script will automatically start the daemon at every startup.  
Place the `temp.py` script on your raspberry desktop, move the `fan.service` file to `/etc/systemd/system/` and give the command `sudo systemctl daemon-reload`. 
To start the newly installed service, type: `sudo systemctl start fan`, to stop it instead type `sudo systemctl stop fan`. 
You can also start it automatically at boot by typing `sudo systemctl enable fan`, You can also stop it at boot type or `sudo systemctl disable fan` to disable it.