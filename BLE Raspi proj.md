## BLE tech info 
- info regarding services and servver clientt relationship
	- https://circuitdigest.com/microcontroller-projects/esp32-ble-server-how-to-use-gatt-services-for-battery-level-indication




## BLE management error < solution > 
- reasons  for BLE management error 
	-  power cycling 
		-  erase the ram and boot up with fresh information 
	- built in blootooth adapter issue 		
		- low voltage warning showing up 
	- fixed by cahnging the version to bluepy 1.1.1 
	
		
		
- steps undertook for  solving bluetooth hardware issues in Rpi : 
	 1.  for fixing the raspberry pi bluetooth issues 
		- https://learn.pi-supply.com/make/fix-raspberry-pi-3-bluetooth-issues/
	2. for fixing the sap driver error while running the status command for bluetooth 
		- https://raspberrypi.stackexchange.com/questions/40839/sap-error-on-bluetooth-service-status
		- command for checking the status    [ sudo systemctl status bluetooth  ]
	3. for solving program issues 
		- use decorator to wrap btle excepption into bluetooth backend exception  
			- https://www.programcreek.com/python/example/97794/bluepy.btle.BTLEException
		    -  while testing sample code for python bluetooth scan 
				-  gattlib error ocured 
					-  fixed using
					-  https://stackoverflow.com/questions/55178684/installing-gattlib-for-pybluez
	4. checking blupy versions 
		- checking 1.1.1 versions compatibitlity
			- file not found error arising  
				- pasted the wifi_config file from etc 
				- changed ever files permission status 
		- checking on version 1.0.5
			- file not found error arising 

### For fixing bluetooth privacy error :
- occurs while cecking the status of bluetooth
	- can be fixed by
		- > sudo service bluetooth restart 

    5. file not found error
    	- checking blutooth status
			- failed to set privacy occured
		- tried out using bluetoothctl from the terminal 
			- recieved datas from isenser 
				- manuufacturer data provides the necessary imformation 
					- https://stackoverflow.com/questions/63572951/how-to-get-desired-values-from-ble-manufacturer-data-flutter
					- B8 : 7C  is the ip adddress of  Isensor
						- transmitted  6 to 7 lengthed hex value string  
					- 00 : A0 is for mike 
					- 79:6D  some ip sending the data when pulse checked
					- while pairing 00 showing org.blue.authentication error 
			- refer research work on hexiwear connection to raspberr pi
				- they used 5.43 
					- to download the bluez 
						- http://scribles.net/
				- https://dzone.com/articles/ble-pairing-the-raspberry-pi-3-model-b-with-hexiwear
					- bluez version 5.5 used   
			- to tr connecting from bluez driver ackage 
				- https://learn.adafruit.com/reverse-engineering-a-bluetooth-low-energy-light-bulb/control-with-bluez
		
		
		
- FOR SETTING UP BEACONTOOL SCANNER 
	- https://github.com/bowdentheo/BLE-Beacon-Scanner		
	
		
##  BLE i/o error 
- happens during lescan command execution 
	- for fixing 
		1.  sudo hciconfig hci0 down 
		2. sudo hciconfig hci0 up


##  Authentication issue 

- using esp32 ( used only for creating the oximeter )
	- https://circuitdigest.com/microcontroller-projects/esp32-ble-client-connecting-to-fitness-band-to-trigger-light#:~:text=To%20connect%20with%20a%20server,and%20try%20connecting%20to%20it.
	- esp32 works as
		- both client 
		- server mode 
			- only prvides data
- middle man attack using gap techinique 
	- https://www.digikey.com/eewiki/display/Wireless/A+Basic+Introduction+to+BLE+Security	
- integrating the company manufactured oximeter with any ble-chip
	- texas instruments info about oxmeter construction 
		- https://www.ti.com/solution/pulse-oximeter?variantid=25892&subsystemid=25897
- authetication was possible for a few seconds usiing 
	- > connect 0connect 00:A0:50

## programs not yet tested 

- https://punchthrough.com/bluetooth-low-energy-peripheral-testing/
- nrf app used in phone 
- ble scanner used 
- oximeter used


## reinstalling python
- never reinstall 
	- causes raspi gui damage ( for any linux system )

### installing bluez package on Rpi3
- https://www.raspberrypi.org/forums/viewtopic.php?t=162528

## ithings reengineered program
- gattcall 
	- pgatt can be used 
- the source code of the application is taken 	
	- written in java
	- the uuid section is studied and gattcall secton is scanned . 


## completed bluetooth data reception steps
- detailed program saved in khaleelrahmanbinseethi as 
	- BLE device character recieve code
	- BLE-Gatt library is used 
	-  in the code 
		-  the reception uart_rx id is pasted .
		-  the reception part is called in the program instead of transmision