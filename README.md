# ZABBIX---Open-Source-Monitoring-Software-for-Automotive-Monitoring

![Alt Text](https://github.com/MagnoMonteCerqueira/ZABBIX---Open-Source-Monitoring-Software-for-Automotive-Monitoring/raw/main/Imgs/1641929639393.jpg)

The first thing that comes to mind when someone is mentioning the monitoring system is pretty simple. People think about server monitoring, and with servers, we usually mean Linux and Windows systems and also network monitoring for all kinds of flavors of switches, routers, firewalls, etc. But by putting so much focus on these standard things we are someway limiting the possibilities of monitoring systems. Zabbix has proven itself as an extremely powerful monitoring tool that can combine and monitor all client infrastructure, no matter if we are talking about the same mentioned servers, network devices, services, applications, or anything else. And most important - Zabbix is truly a 100% open-source product, which allows anyone to use all listed functionalities for free.
In this article, I will try to cover more or less the theoretical models on how you are able to monitor your vehicle fleet with minimal to no cost at all. Please, keep in mind that no doubt there are systems available that are created exactly for the same purpose I will cover here. Maybe they are more reliable, maybe they lack less effort to achieve the desired result. But that is the exact reason why this model is mostly theoretical with the main purpose to show that it is hard to put Zabbix in some functionality boundaries, and usually, the only limitation is our imagination. And it is up to you, to treat this information for pure entertainment or try to implement it in a place where you find it suitable.

Let's get straight to the point. You don't have to own a huge logistics company with a thousand vehicle fleet to understand it. With simple words - if you or any of your relatives own a car, you should be aware that cars tend to break. Just like it usually happens, there could be many types of issues, starting with a flat tire and ending with some ongoing damage in the gearbox or engine. It is important to understand, that vehicles themselves are becoming smarter and smarter. If in the past it was a purely mechanical device then nowadays it is an extremely complicated electronic system on top of that mechanical device, that is able to diagnose the slightest deviations from accepted norms that are set by the manufacturer and inform about this malfunction either with an indicator light on your dash or simply with log message that will be accessible only when read with specialized software or tool.

![Alt Text](https://github.com/MagnoMonteCerqueira/ZABBIX---Open-Source-Monitoring-Software-for-Automotive-Monitoring/raw/main/Imgs/1641931647053.jpg)


Keep in mind that malfunctions in vehicles are not as simple as boolean ( works or not ), in most cases issue is noticed before the car is not able to move forward, and the purpose of that is to be informed and fix the issue before it has grown to defect that actually prevents a vehicle from functioning.
And now think about this from an automotive business perspective. We may be talking about hundreds of vehicles that are always on the move to deliver something or someone in time. It should be straightforward that in such a niche each of these vehicles should make close to thousand kilometers per day.


![Alt Text](https://github.com/MagnoMonteCerqueira/ZABBIX---Open-Source-Monitoring-Software-for-Automotive-Monitoring/raw/main/Imgs/1641932679658.jpg)

Thankfully, as mentioned previously, the smart diagnostic system will let you know about all potential problems. On the other side, the driver of the vehicle usually has nothing to do with its repairs or technical condition. So in a perfect world, we should have a few technical employees, that would simply ask returning driver whether everything is fine with the car after his shift, are there some errors, and ideally, connect with diagnostic software to read its logs to make sure that everything actually is ok. If it's not ok, information should be passed to the technical department to move this vehicle to the maintenance.
Why such pressure? Well, remember that most of these notifications serve as a warning, that something is not working as it should, but currently it is not causing harm. However, if it will be ignored, there is a high chance that at some point vehicle would not be able to continue its way to the destination.


![Alt Text](https://github.com/MagnoMonteCerqueira/ZABBIX---Open-Source-Monitoring-Software-for-Automotive-Monitoring/raw/main/Imgs/1641933465952.png)


So this is the time when Zabbix joins the conversation. Imagine if all this data transfer from vehicle diagnostic system to responsible employees would happen automatically, with potential error prioritization and escalation to further levels if any vehicle has an ongoing issue that remains active for multiple days. And remember that Zabbix is a truly free and open-source system, which means that we could achieve this result for free. And we are absolutely not limited to DTC ( Diagnostic Trouble Codes ) readings. Combining this ecosystem with the recent Zabbix 6.0 LTS release, we are able to get geomap with the current location of any vehicle from our fleet. With a little effort, we can also get speed measurements, long stops, starts, and much more.
This is the part when tested, but still theoretical model comes into action. By now we are aware, that a car is way smarter than it may look, and it gathers and stores a lot of useful information. However, the Zabbix monitoring system as per the most common standard sits somewhere in our headquarters and monitors generic metrics of our IT infrastructure. So how could we potentially get this information from our vehicle to Zabbix?

![Alt Text](https://github.com/MagnoMonteCerqueira/ZABBIX---Open-Source-Monitoring-Software-for-Automotive-Monitoring/raw/main/Imgs/1641934244741.jpg)

Since all information is stored in ECU (Electronic Control Unit), there is also a way to read it. And it is achieved through OBD (On-Board Diagnostic) socket through the standardized protocol. Just like anything else OBD has multiple versions or protocols of communications, but if we are talking about seamlessly modern cars, most likely we are talking about OBD-II which included Electronic signaling and messaging format.
And exactly OBD-II will help us to gather all information from the vehicle, to further transfer it to our Zabbix monitoring system. Initially, this may yet sound very unclear, because we have some kind of socket to access our ECU, but how can we actually gather some meaningful data? For that, we will need ELM327






