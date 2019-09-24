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
