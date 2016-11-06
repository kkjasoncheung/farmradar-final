# farmradar-final

Arduino Code File includes all codes for sensors.
Streamer.rb is a ruby script to open a multi-threaded application which parses sensor data from a serial port of an arduino
in the background.

dash-int is the folders that contains the Sinatra app for the front end using the Dashing framework that connects to our sensors and hardware.

The DevPost link to this project is: https://devpost.com/software/farm-radar

<hr>
#Farm Rada is a modular remote sensing system that scans agricultural and environmental data and gives real time feedback.

#Inspiration & What it does?
This project is created during Major League Hacking (MLH) Electric City Hacks 2016.

The inspiration for this project started after reading about big data in Agri-tech and the use of drones in the farm management system. Researchers are trying to use drones to find out the quality of their crops on a large scale via imaging. What if by using modular ground level sensors we could also easily assess the quality of the farmland at the current time and also be able to monitor long and short term trends? This will also allow us to cross check with drone imaging and all together create a big data warehouse which could give a lot of information to users.

The problem is sensors/server are expensive, are hard to setup for non-technical people and the interfaces are user friendly. As a farmer, I want to have access to my farms current state from wherever I am in the world and if I ever decide to expand my farm, I should be able to connect more sensors easily. Farm yard does just that. Our dashboard allows you to look into the state of your farm in one glance and look for any potential hazards. It is connected into a distributed server in such a way that, adding a new sensor is as easy as plugging one wire.

#How we built it
Hardware
The hardware system is designed to be modular and portable. The central part of the system is a box with 8 separate input ports, along with the microcontroller (ATmega2560) inside. There is also a Nest Camera on the top of the box, mounted on a motor. The box is designed to be modular and can recognize incoming sensor with set-ups from the dashboard. The box is open to most of the digital and analog sensors. (ex. soil-Moisture, light, fire, water level, heat-motion, temperature, humidity, etc.). 

#Dashboard
The software system is based on Sinatra, the reason we used Sinatra over Ruby on Rails is because Sinatra is very lightweight. Using Sinatra, we would do a GET request to a server to get a JSON file, which is then parsed by the controllers to separate data out from 8 different sensors that are fed in at the same time using a serial port on our micro-processor. This data is then connected to a dashing framework which is based on jQuery, Bootstrap, HTML5 and SCSS front end in real time. We run a multi-threaded program within the controller which does a periodic polling every 1s and gets new data.

For more information, please visit https://devpost.com/software/farm-radar

Thank you.
