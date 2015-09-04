In this menu you're able to set advanced wireless settings.

# Index #
  * [Introduction](GUIWirelessAdvanced#Introduction.md)
  * [Enable AfterBurner](GUIWirelessAdvanced#Enable_AfterBurner.md)
  * [Hide SSID](GUIWirelessAdvanced#Hide_SSID.md)
  * [Set AP Isolated](GUIWirelessAdvanced#Set_AP_Isolated.md)
  * [802.11b/g Data Rate (Mbps)](GUIWirelessAdvanced#802.11b/g_Data_Rate_(Mbps).md)
  * [Multicast Rate (Mbps)](GUIWirelessAdvanced#Multicast_Rate_(Mbps).md)
  * [802.11n MCS Index](GUIWirelessAdvanced#802.11n_MCS_Index.md)
  * [Basic Rate Set](GUIWirelessAdvanced#Basic_Rate_Set.md)
  * [Regulatory Mode](GUIWirelessAdvanced#Regulatory_Mode.md)
  * [Fragmentation Threshold](GUIWirelessAdvanced#Fragmentation_Threshold.md)
  * [RTS Threshold](GUIWirelessAdvanced#RTS_Threshold.md)
    * [What is RTS](GUIWirelessAdvanced#What_is_RTS.md)
  * [DTIM Interval](GUIWirelessAdvanced#DTIM_Interval.md)
  * [Beacon Interval](GUIWirelessAdvanced#Beacon_Interval.md)
  * [Enable Frame Bursting](GUIWirelessAdvanced#Enable_Frame_Bursting.md)
  * [Extended Mode](GUIWirelessAdvanced#Extended_Mode.md)
  * [Enable Radio](GUIWirelessAdvanced#Enable_Radio.md)
  * [Date to Enable Radio](GUIWirelessAdvanced#Date_to_Enable_Radio.md)
  * [Time of Day to Enable Radio](GUIWirelessAdvanced#Time_of_Day_to_Enable_Radio.md)
  * [Radio Power](GUIWirelessAdvanced#Radio_Power.md)
  * [Enable WMM](GUIWirelessAdvanced#Enable_WMM.md)
  * [Enable WMM No-Acknowledgement](GUIWirelessAdvanced#Enable_WMM_No-Acknowledgement.md)


---


# Introduction #
This page contains some advanced wireless settings. Usually you do not want to change most of the settings on this page since they can easily make your WiFi connection unstable.

However, some settings will usually optimize your connection.

Some settings might not be available on your router due to the wide range of WiFi cards in Asus routers.


---


## Enable AfterBurner ##
AfterBurner is a proprietary technology of Asus enabling up to 125Mbit/s transfer speeds for 802.11g connections.

This technology is not an official 802.11 standard and thus it does not work with most WiFi cards. Unless you have an Asus AfterBurner enabled card you can't use the advantages of this functionality.


---


## Hide SSID ##
This option allows you to broadcast your SSID (WiFi network name).
The SSID is required to connect to your WiFi network, when hidden you must fill in the name manually on your WiFi clients.

Hiding the SSID gives a false sense of security, it's a matter of seconds for a hacker to find out the SSID since it's openly broadcasted by connected clients.


---


## Set AP Isolated ##
This option is ideal for public access points.

It disallows WiFi clients to connect to each other and thereby reducing the risk of unwanted file sharing etc.

The clients will be able to connect to the internet when the setting is set to "Yes".


---


## 802.11b/g Data Rate (Mbps) ##
The recommend setting is "Auto" to maximize performance.

With this option you may limit the maximum speed of your access point.

note that the maximum speed is shared with all the clients connected to your wireless network.


---


## Multicast Rate (Mbps) ##
With this setting you can change the maximum speed for [multicast](http://en.wikipedia.org/wiki/Multicast) networking.

Multicast is usually used when you stream music or video.

It's recommended to set this setting to "auto" to auto balance the performance and increase compatibility with clients.


---


## 802.11n MCS Index ##
This option allows you to limit the maximum speed for 802.11n WiFi networks.

For a lookup table I recommend this Wikipedia article: [Data Rates](http://en.wikipedia.org/wiki/IEEE_802.11n-2009#Data_rates)

Note that 802.11n(draft 1) has a 800ns GI and 802.11n(draft 2/final version) has a 400ns GI.
The WL500W has 802.11n draft 1 for example.

The recommended setting is "Auto" for maximum performance.


---


## Basic Rate Set ##
The recommended setting is "default" for maximum compatibility with WiFi clients.

WiFi cards support a wide range of transfer speeds, with this setting you can disallow clients that do not support a specific rate.

**The standard 802.11g rates: 1, 2, 5.5, 6, 9, 11, 12, 18, 24, 36, 48 and 54 Mbit/s**


---


## Regulatory Mode ##
The default setting is 802.11d, which is supported by most modern WiFi Cards.

#### Off ####
> Don't use any regulatory modes. Use this mode only when you have compatibility issues with the other modes.

#### 802.11d ####
> Commonly known as the "Global Harmonization standard".

> This standard automatically adjusts its allowed frequencies, power levels and bandwidth accordingly to the country it's located in. This means that manufacturers don't need to make country specific products.

> This mode is supported by most modern WiFi cards.

> [More information](http://en.wikipedia.org/wiki/802.11d)

#### 802.11h ####
> This standard is newer than the 802.11d standard and was originally designed for European regulations. Today it can be used in many other countries.

> The standard solves interference problems with e.g. satellites and radar using the same 5 GHz band as 802.11a or 802.11n dual-band access points.

> Some Intel WiFi cards are known to work better with this mode than 802.11d.

> [More information](http://en.wikipedia.org/wiki/IEEE_802.11h-2003)


---


## Fragmentation Threshold ##
This is an advanced setting that may make your WiFi unstable and it's recommended to leave it be.

**The default value is: 2346**

#### What is fragmentation ####
> The router uses fragmentation to divide 802.11 frames into smaller pieces which are separately send to a client.
> The client will send an acknowledgement (like saying "I received the frame properly") back for every frame it receives.

> Fragmentation only works with unicast (a single destination) addressed packages.
> To minimize the load on the WiFi network it does not work with broadcast or multicast (multiple destinations) addressed packages.

> Fragmentation can increase reliability of frame transmissions when multiple clients are connected since it will minimize the chance of having collisions.

  * A collision happens when the Access point receives 2 or more frames at the same time (from multiple clients). The Access point will have to drop all frames, and thus need to be send again by the clients. The less collisions you have, the higher total speed you're able to get.


A good range for fragmentation values is between 256 and 2048.
2048 and higher will disable fragmentation.


---


## RTS Threshold ##
This is an advanced setting that may make your WiFi unstable and it's recommended to leave it be.

**The default value is: 2347**

The WiFi clients need to support RTS/CTS to make use of this option.

#### What is RTS ####
> RTS means Request to Send.

> To keep this explanation simple, a little story:

> Imagine having 2 laptops connected to your router. Both laptops are too far away to communicate with each other directly, but the router between the laptops allows them to communicate through the router.
> When both laptops send a frame at the same time the router will need to drop both frames (frame collision). This is of course an unwanted situation.

> With RTS enabled the laptops will first send a Request To Send message to the router. When the router hasn't any other transmissions going on it will send back a Clear To Send (CTS) message back. After the laptop receives the CTS it will send the frame.

> This RTS/CTS communication reduces frame collisions when multiple clients are connected.


To optimize RTS/CTS it's recommended to use a value around 500.
2347 will disable RTS/CTS.

Usually turning this option on will slow down your network.


---


## DTIM Interval ##
DTIM is a short for "Delivery Traffic Indication Message".

DTIM allows WiFi clients to go in energy saving mode without connection loss.
As soon as a sleeping client receives a DTIM message it will become active again to receive the data available.

A low value will cause WiFi clients to enter energy saving mode only for a short period of time. A high value will cause the client to wait longer till it may enter energy saving mode but will be able to stay in energy saving mode longer.

The default value is "1".


---


## Beacon Interval ##
The amount of time between beacon transmissions. Before a WiFi client enters energy saving mode, the WiFi client needs the beacon interval to know when to wake up to receive the beacon (and learn whether there are buffered frames at the access point).

The default value is "100".


---


## Enable Frame Bursting ##
Frame Bursting is a [Quality of Service](http://en.wikipedia.org/wiki/Quality_of_service) method to enable higher throughput.

When enabled it allows WiFi clients to send up to 3 frames at once before it has to wait again. Normally clients only send one frame at a time.

It's not recommended for more than 2-3 wireless clients or there can be a negative results and throughput will be affected.


---


## Extended Mode ##
Select between a range of wireless functionalities.

#### AP or WDS ####
> The default value.

> In this mode the router is able to act like an Access Point and will route the wireless connections the same way as wired connections.

> Also Wireless Distribution Systems can be used to link multiple Access Points together wirelessly.

#### Station ####
> This way the router will act like a WiFi client and will be able to connect to other WiFi networks.

#### Ethernet Bridge ####
> In this mode the router will be able to route wired connections straight trough wireless. You can compare this mode with a wireless USB stick, but connected instead via a networking cable.


---


## Enable Radio ##
Like the name suggests: turn on or off wireless functionalities.


---


## Date to Enable Radio ##
This setting allows you to turn on WiFi only on certain days by selecting the tick-boxes.


---


## Time of Day to Enable Radio ##
This setting allows you to turn on WiFi only between certain times.

When it's set to 00:00-23:59 it will be turned on the entire day.


---


## Radio Power ##

This setting allows you to change the maximum power and will limit how far the WiFi network reaches.

All the values are in milliWatt since [r1974](https://code.google.com/p/wl500g/source/detail?r=1974).

A value between 0 and 400 can be entered. The default value is 50 however.

When the value is set to 0 the default (maximum) power will be used: 1496 mW

Please keep in mind that a high power level can increase noise on the channel and might decrease transfer speeds over WiFi.


---


## Enable WMM ##
This is another [Quality of Service](http://en.wikipedia.org/wiki/Quality_of_service) method to optimize networking.

WMM prioritizes traffic according to four types of networking: voice, video, best effort, and background.

It's a good idea to enable this when you use a WiFi phone or stream a lot of video via the network.

WMM only works with clients supporting WMM. Most clients do so today.


---


## Enable WMM No-Acknowledgement ##
This option is the same thing like "Enable WMM", but only works when WMM is turned on.
The key difference is that the router will not check if a WiFi client is compatible.

It's recommended to disable this functionality since it might cause instability of the network as soon as an incompatible client is connected.