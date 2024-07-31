<!-- title -->
# CSCE4910&4915 - COMPUTER ENGINEERING SENIOR DESIGN PROJECT

##### Project: Water Monitoring System for Automated Inland Shrimp Production
##### Instructor: Dr. Robin Pottathuparambil
##### Sponsor: Dan Combe
##### Team: Eagle Squad
##### Year: 2021-2022
##### Contact support: qiangsi001@gmail.com
<br />



<!-- toc -->
Table of Contents
----
- [Introduction](#heading)
- [Description](#heading-1)
- [Team Members](#heading-2)
- [Proposition](#heading-3)
- [Implementation](#heading-4)
- [Organization of the Project](#heading-5)
- [Summary](#heading-6)
- [Acknowledgments](#heading-7)
- [References](#heading-8)  
<br />



<!-- pic_of_ghost_shrimp -->
![ghost_shrimp](https://acuariopets.com/wp-content/uploads/2020/06/d0497c5c7380e1c0220974e6f4e0b99f.jpg?ezimgfmt=ng%3Awebp%2Fngcb6%2Frs%3Adevice%2Frscb6-1)  
[1]  
<br />



<!-- intro -->
<a name="heading"></a>
## Introduction
&ensp;&ensp;&ensp;&ensp;&ensp;Annually, US imports several thousand metric tons of shrimp every year. US imported 698,358 metric tons in 2019[2]. These imports are done mainly from India, Indonesia, Ecuador, and other countries. The cost is around $8 per kg (2.2lbs.) and when it is sold in the market the cost doubles[3]. Also, based on the type of the shrimp, the cultivation may require salt water or fresh water. Currently, there are only few places in US where shrimp is cultivated inland.  
<br />



<!-- project_description -->
<a name="heading-1"></a>
## Description
&ensp;&ensp;&ensp;&ensp;&ensp;US imports 90% of its shrimp and it is not cheap. The goal of the project is to reduce the imports and eventually reduce cost per pound. In order to achieve these goals, shrimp must be cultivated inland in a controlled environment. The cost of the controlled environment and its supervision must be cost effective and easy such that the cost of the shrimp per pound is cheaper than imports.  
<br />



<!-- team members -->
<a name="heading-2"></a>
## Team Members
* Fuad Bani Salameh&ensp;&ensp;&ensp;-- Minerals Subsystem, Salinity Subsystem, Turbidity Subsystem, Wireless Communication, Aquarium light
* Joe Selvera&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;-- Mobile app, Temperature Subsystem, Main Controller, Cellular  
* Munachimso Nwosu &nbsp;&nbsp; -- Ammonia Subsystem, PH Subsystem, Backup Batteries
* Qiang Si&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&nbsp;-- Feed Subsystem, Oxygen Subsystem, PCB Design, Universal Power Adaptors, Enclosures  
<br /> 



<!-- project_proposition -->
<a name="heading-3"></a>
## Proposition
&ensp;&ensp;&ensp;&ensp;&ensp;Develop an automated system that will control the growth of the shrimp in order to reduce the cost of the shrimp production, thus decreasing the amount of imported shrimp. As a result, the implemented system will be cost effective.  
<br />



<!-- Implementation -->
<a name="heading-4"></a>
## Implementation
&ensp;&ensp;&ensp;&ensp;&ensp;※Main Controller: The eight subsystems connect to a soft wireless access point and transfer the acquired data to it wirelessly. The SoftAP then transfers the data to the main controller to be processed and sent to the cloud through either WiFi or LTE.

&ensp;&ensp;&ensp;&ensp;&ensp;※Subsystems: To grow shrimp, our system controls eight important factors when growing shrimp: Ammonia, Feed, Minerals, Oxygen, pH, Salinity, Temperature, and Turbidity.

&ensp;&ensp;&ensp;&ensp;&ensp;※Cloud: The cloud consists of MQTT messages sent to AWS IoT Core, then processed through a Lambda function, and finally stored into DynamoDB.

&ensp;&ensp;&ensp;&ensp;&ensp;※Mobile App: The mobile app connects to AWS DynamoDB to retrieve and display the acquired data to the user.  
<br />



<!-- functionality_of_eight_subsystems -->
<a name="heading-5"></a>
## Organization of the Project
###### Salinity Subsystem:       
&ensp;&ensp;&ensp;&ensp;&ensp;  ※monitors and controls the salinity (salt ratio) of the water for growing healthy shrimp.
###### Minerals Subsystem:
&ensp;&ensp;&ensp;&ensp;&ensp;  ※monitors and controls the minerals for growing healthy shrimp.
###### Turbidity Subsystem:      
&ensp;&ensp;&ensp;&ensp;&ensp;  ※monitors and controls the turbidity of the water necessary for the healthy growth of shrimp.
###### Wireless Communication:   
&ensp;&ensp;&ensp;&ensp;&ensp;  ※receives all the acquired sensor data on the main controller using wireless protocols.

----
###### Temperature Subsystem:    
&ensp;&ensp;&ensp;&ensp;&ensp;  ※monitors and controls the temperature of water tank for growing shrimp, and sends the temperature value to the main controller. 
###### Wireless Communication:   
&ensp;&ensp;&ensp;&ensp;&ensp;  ※sends the received data to the cloud using wireless communication.
###### Mobile app:               
&ensp;&ensp;&ensp;&ensp;&ensp;  ※a cloudbased mobile app to monitor all subsystems and report to the user. Also, in the event of WiFi not being available, the system will switch to cellular communications to send its data to the cloud.

----
###### Ammonia Subsystem:
&ensp;&ensp;&ensp;&ensp;&ensp;  ※monitors and controls the ammonia level needed to grow shrimp.
###### PH Subsystem:        
&ensp;&ensp;&ensp;&ensp;&ensp;  ※an automatic acidity controller subsystem with a pH probe to make sure that the acidity of the water is appropriate for shrimp growth and sends the pH value to main controller.
###### Backup Batteries:  
&ensp;&ensp;&ensp;&ensp;&ensp;  ※each subsystem has its own backup backup battery to prevent power outage.       


----
###### Feed Subsystem:
&ensp;&ensp;&ensp;&ensp;&ensp;  ※an automatic feed controller subsystem for periodic feeding, and sends the status message to main controller.
###### Oxygen Subsystem:            
&ensp;&ensp;&ensp;&ensp;&ensp;  ※an automatic oxygen controller subsystem to meet the desired levels of oxygen for the shrimp to survive and grow, and sends the oxygen level value to the main controller.  
###### PCB Design:  
&ensp;&ensp;&ensp;&ensp;&ensp;  ※each subsystem has its own PCB to reduce sizes(easy to manage), chance of errors, and possibilities of short circuit.  
###### Enclosures:  

Subsystems | Length(cm) | Width(cm) | Height(cm) |
:---: | :---: | :---: | :---: |
Main | 18.6 | 9.6 | 7.3 |
Mineral | 23 | 15 | 8.7 |
Salinity | 23 | 15 | 8.7 |
Turbidity | 23 | 15 | 8.7 |
pH | 23 | 15 | 8.7 |
Ammonia | 23 | 15 | 8.7 |
Temperature | 40 | 35 | 12 |
Oxygen | 23 | 15 | 8.7 |
Feed | 19.5 | 14.5 | 13 |

(**note**: main system's enclosure is 3D printed, the rest are purchased)  
<br />



<!-- summary -->
<a name="heading-6"></a>
## Summary
&ensp;&ensp;&ensp;&ensp;&ensp;Through this project, we as a team have learned a lot about 
**testing hardware components, interface with various sensors, soldering, PCB design, CNC milling, 3D printing, circuit schematics, programming languages, network procotol, IoT, Amazon DynamoDB(NoSQL database service), AWS Lambda, App, interface with various sensors, and most important for integration of overall system.** We have concluded that our project works on a small scale, and can be expanded upon for large shrimp production.  
<br />



<!-- people we want to thank for -->
<a name="heading-7"></a>
## Acknowledgments
* Robin Pottathuparambil [Project Manager]
* Dan Combe [Sponsor]
* Alejandro Olvera [Lab Technician]  
* UNT Computer Engineering Department  
<br />



<!-- links -->
<a name="heading-8"></a>
## References
* [1] Gohost Shrimp Picture(https://acuariopets.com/how-to-take-care-of-pregnant-ghost-shrimps/)
* [2] NOAA’s Trade data(https://www.st.nmfs.noaa.gov/apex/f?p=213:19:10985154164477::NO:::)
* [3] Undercurrent News(https://www.undercurrentnews.com/2020/07/02/us-shrimp-imports-finally-crashed-in-may-latest-noaa-trade-data-show/)
