# OpenClock
Raspberry Pi Pico / ESPHome based central heating controller

![image](https://github.com/user-attachments/assets/c987b934-528c-4df4-ab44-8cef0a9c58c7)

![image](https://github.com/user-attachments/assets/bf844d99-962a-4d8e-8c5c-6d56b02202bd)



# Background
I bought a house that had a "dumb" heating controller - a heating clock that switched zones on and off on a schedule. It had three zones, as my house has a hot water, upstairs and downstairs loop.
I replaced it for a Nest Learning Thermostat 3, and was very unimpressed with it - It only had water and one zone, and the app design was terrible. For me (having an oil fired boilder), I wanted to turn the heating on for an hour in the morning to get the house warm, and give me hot water for a shower, and that's about it. Obviously as the name suggests, the Nest Thermostat wanted to get the house to a temperature and hold it there, which didn't work for me.

To fix this, I designed OpenClock - an ESPHome based heating clock built around readily available parts that would integrate into my already mature smart home system, giving me the ability to make the control of this clock as simple or as complex as I wanted. It was also a learning tool for me, being the second time I've designed circuitry for UK mains (240V) applications.

While I wouldn't recommend anyone build this (as I have limited experience with designing mains application devices), and this repo is more for demonstration purposes, I have been using OpenClock for over a year without issue.

# Features

* Designed to screw to a UK single gang backbox
* 3 Heating zones, can be switched on and off independantly
* Runs ESPHome on a RPi Pico, so firmware can be modified

# Heating systems known to work

Only tested in my house - has an oil fired boiler, which is controlled in two ways:

1. The water "zone" sends mains power directly to the water "zone" valve - this valve opens, and a switch inside the valve then powers the boiler.
2. The room "zones" send mains power to a room thermostat - this thermostat has the final say over whether the room "zone" valve opens, which when opened, powers the boiler as above.
 
# The benefit of hindsight

While OpenClock has worked well for over a year, having spent some time with it, I now know how I would it different - and probably will. If I was doing this centralised control method again, I would buy a Shelly relay - these guys have far more experience than me with designing safe electronics, and their hardware is small enough to fit in a UK backbox. One of their relays probably costs less than the price of the PCBs alone.

However, I've come to strongly dislike my room thermostats - they're loud when switching, difficult to use, and are very feature-light. By this I mean, they turn on and off with temperature in a room.
To fix this, I would hardwire the mains wires where OpenClock is at the moment, so the room thermostats are receiving power all the time, and install something like the Sonoff NSPanel. This would add so many more options into the rooms where the thermostats are mounted.
