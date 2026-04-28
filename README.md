# IoT-project

## Story/Scenario

The user named Joosep comes home and wants to relax after a long day of working. He likes gaming and has a beast of a setup. He has his IoT system set up so that the automatic activation happens between 6 PM and 12 AM. When the user is away for some time, then the system will shut down / go to sleep mode.  

During that timeframe he sits down on his chair and the system will detect them and activate the gaming mode. It will automatically create the necessary atmosphere by turning the lights, LED strips will turn on/off. The blinds work automatically and the room will monitor the CO2/TEMP levels and turn the AC on/off. The LED strip and OLED screen will give feedback to different scenarios, for example, if it's time to take a break or if the user gets too angry, then calm them down.  

When Joosep is hungry or thirsty, he waves his hand at the snack or drink dispenser to get the snack or drink he needs at that moment. When the drinks are running low, the dashboard will let him know when to restock.  

## Potential problems/challenges
   
The chair sensor might get tricked by pets or bags, while snack and drink dispensers can jam or miscount. Environmental sensors (like CO2 or temperature) can give bad readings if placed near heat sources or windows.   

Wi-Fi or Bluetooth connections can drop or interfere with each other, causing delays or failures. Waking up the PC automatically isn’t always reliable, and keeping everything synced will require constant tweaking.  

There will be false alerts. Too many notifications ("Take a break!" "Snack empty!") can become annoying fast. The noise and vibration sensors might dim the lights unnecessarily if the user slams the desk or plays a loud game.  

An always-listening microphone is a privacy concern, even if it’s just for noise detection. Cheap iot devices are easy targets for hackers, and auto ordering snacks or drinks could go wrong, like accidentally buying 50 sodas because of a bug.  

The setup might encourage you to sit for too long, which isn’t great for the user's health. Dispensers could also drop snacks or drinks unexpectedly, causing a mess.  


## Implementation possibilities  

- We can use a pressure sensor under the chair AND a distance sensor to detect if the person is sitting down.   
- We will use a small OLED screen that shows a message to the user that the mode is activated + other notification messages.   
- We can use a motor that lowers the monitors down to the table.   
- We will use led strips that turn on when the mode is activated. They also flash when it is time to take a break.  
- Also the snack dispenser activates, it uses a distance sensor to detect when the user puts their hand out to dispense snacks.  
- Same for the drink dispenser - uses a distance sensor to detect a hand to dispense drinks (cans). There is also a distance sensor at the fill up opening and at the exit that removes/adds one from/to the total amount of drinks. There is also a temperature sensor to monitor the coldness of the drinks.  
- Both the drink and snack dispenser send notifications if their stock is low.  
- A light sensor is also near the window of the room to detect if it is bright outside, if true, then it pulls down the curtains with a motor.  
- There is also a co2/temp sensor in the room. If the room is too hot/stuffy then it turns on the AC.  
- There is a microphone and a movement sensor (knock sensor or M5 stick maybe?) that detect loud noises and desk slams. They will display a calming message to the user on the OLED screen and turn the LED strip colors in the room to more calming ones.  

We will use MQTT to send messages between the nodes and NodeRed to connect these nodes.