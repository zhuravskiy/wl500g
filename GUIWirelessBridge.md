# Index #
  * [Introduction](GUIWirelessBridge#Introduction.md)
  * [AP Mode](GUIWirelessBridge#AP_Mode.md)
  * [Channel](GUIWirelessBridge#Channel.md)
  * [Connect to APs in Remote Bridge List](GUIWirelessBridge#Connect_to_APs_in_Remote_Bridge_List.md)
  * [Allow anonymous](GUIWirelessBridge#Allow_anonymous.md)
  * [Remote Bridge List](GUIWirelessBridge#Remote_Bridge_List.md)


---


# Introduction #

In this menu you'll be able to set up a Wireless Distribution System (WDS).

Since setting up a WDS is different than just entering settings, a small introduction:

A WDS can consist of 3 types of stations:
  * Main station (AP Only): the router connected to the internet for example.
  * Switch station (Hybrid): the router distributing both wireless and wired from the Main or other Switch station. In this mode a similar effect as with repeaters can be expected, making the wireless network available over great distances.
  * Base station (WDS Only): the router distributing only wired connections from the Main or Switch stations.

The downside of WDS is that the theoretical maximum throughput is halved each hop. Thus the more routers are between the client and the Main station, the slower the network will be.

Some notes:
  * For WDS to work at least 1 router should be configured as a regular Access Point for the other routers to connect to.
  * All stations should be configured with the same encryption, channel and SSID settings.
  * Generally it's advised to avoid creating loops.

Read more about WDS [here on Wikipedia](http://en.wikipedia.org/wiki/Wireless_Distribution_System)



---


# AP Mode #

Choose between the several modes described above here.

Make sure that in the [Wireless Advanced page the "Extended Mode" is set to "AP or WDS"](GUIWirelessAdvanced#Extended_Mode.md).


---


# Channel #

For a WDS mode (WDS Only/Hybrid) the Channel should be set to a fixed channel.

For all stations this channel must be the same!

It's a good idea to set the Main station to a fixed channel as well so the other stations don't require a sudden configuration change.

More information about channels? Check the [Wireless Interface page](GUIWirelessInterface#Channel.md)!


---


# Connect to APs in Remote Bridge List #

Selecting yes will cause the switch or base station to connect to other stations.


---


# Allow anonymous #

Selecting yes will cause other stations to connect to this station without being listed in the Remote Bridge List as long as the [encryption](GUIWirelessInterface#Authentication_Method.md), [channel](GUIWirelessInterface#Channel.md) and [SSID](GUIWirelessInterface#SSID.md) are the same.

Beware of loops.


---


# Remote Bridge List #

In this list you can enter known stations MAC addresses.

The MAC address here does not contain colons (:) or dashes (-).

example: 001122334455