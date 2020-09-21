# Chargery
Retrieve data from chargery BMS BMS24T or BMS16T or BMS8T through rs232 to USB cable and post to MQtt server. 


##### Read installation step after the following notes 

##### Note1: change the line devName = '/dev/ttyUSB0' to suit your USB connection port

##### Note2: if your MQTT server is password protected uncomment client.username_pw_set and replace username and password strings with your login detiails

##### Note3: if your mqtt server is on another system replace the ipaddress 127.0.01 and port 1883 as the case may be

##### Note4: you have to install paho-mqtt using pip; run sudo pip install paho-mqtt


##### Default Publish topics: 
1 chargerybms/watthour 

2 chargerybms/amphour 

3 chargerybms/batteryvolt 

4 chargerybms/cellhigh 

5 chargerybms/celllow 

6 chargerybms/maxvolt =maximum cell voltage

7 chargerybms/current 

8 chargerybms/modename =modename is discharge, charge or storage

9 chargerybms/modeint =0,1 or 2 corresponds to modename

10 chargerybms/temp1

11 chargerybms/temp2 

12 chargerybms/soc 

13 chargerybms/aggimped =impedance of battery string


##### Note5: if you need individual cell voltages and cell impedances published, uncomment same in the script

##### Note6: if you don't have pyserial install from pip


## Installation steps:

It is assumed that you have mqtt server, pyserial paho-mqtt installed

1a) copy chargery.py to /home/pi directory

1b) create a a log file named chargery.log in /home/pi

1c) make the log file writable if it's not


2) copy chargery.service to /lib/systemd/system directory

3) run the following commands  in terminal

	sudo chmod 644 /lib/systemd/system/chargery.service
	
	sudo systemctl daemon-reload
	
	sudo systemctl chargery.service
	
	sudo systemctl start chargery.service
	


###### Give feedback so we can improve on it.


