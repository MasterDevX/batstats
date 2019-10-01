# batstats
A simple bash script to get current battery status on Linux
### Provides info about
- Status (charging / discharging)
- Current / max voltage (V)
- Amperage (mAh)
- Capacity (percentage)
### Depends on
- bash
- bc
### Note
This thing should work on most devices, but here are some instructions and explanations what to do if it don't.<br>
This tool provides information based on variable values of ```power_supply``` class. And because of some vendors just love to modify kernel as they want, the ```power_supply``` class structure may vary from device to device (especially on Android devices), so some data in output might be missing or incorrect. The variable names used in this script are equal to variable names in the original Linux kernel. You can find more info about ```power_supply``` class <a href="https://www.kernel.org/doc/Documentation/power/power_supply_class.txt">here</a>. You can also get a list of your variables using ```cat /sys/class/power_supply/battery/uevent``` and if their names don't match the original names, you can easily edit them in script code. It is also possible that in some retarded kernels measurement units are changed (like ```mAh``` instead of ```µAh```), so you also may need to change division coefficient in code (come on, there are less than 30 lines of code, don't be lazy :D).
### Installation
Download ```batterystats``` script, copy it to any directory listed in your ```PATH``` variable (e.g. /usr/bin/) and make it executable using ```chmod +x batstats```.
### Usage
Once installed, you can simply execute ```batstats``` command in terminal to get information about battery. You can also combine ```batstats``` with ```watch``` applet (for example, ```watch -n 5 -t batstats``` will refresh information each 5 seconds).
### Output example
```
Current battery information
---------------------------
Status: Charging
Capacity: 99%
Voltage: 4.180V / 4.200V
Amperage: +196mAh
```
