In this menu you're able to tune up WiMAX settings.

# Index #
  * [Introduction](GUIUSBNetworkDevicesWiMAX#Introduction.md)
  * [General parameters](GUIUSBNetworkDevicesWiMAX#General_parameters.md)


---

# Introduction #
This page contains some additional WiMAX settings, all of them are not required.


---

# General parameters #
## Set as WAN Connection Type by default ##
This checkbox allow to make WiMAX connection as default WAN. Checked state indicate that parameter **WAN Connection Type:** at page **IP Config - WAN & LAN** is **WiMAX**.  Unchecking of it will set parameter **WAN Connection Type:** to value **Auto**. Any changing of this checkbox requires router restart.


## SSID ##
Service set identifier is a name that identifies a particular !WiMAX wireless network.
Default value is blank, it means **@yota.ru** will be used.
Known WiMAX identifiers:
  * Yota - **@yota.ru**
  * Comstar - **login:pass@wimax.comstar-uts.ru**
  * Mezon.lt - **@mezon.lt**

## Check connection ##
When enabled, this setting allows periodic test of the connection by sending a series of ping packets to the ISP gateway.
Results and time of packets circulation are displayed at page [Status & Log - WiMAX](GUIStatusLogWiMAX.md).

It's possible to add your own script **post-check-connection** to reflect connection check fails.
Location and content rules are common and described in [UserScripts FAQ](UserScripts.md). Arguments:<br>
$1 - WiMAX interface name<br>
<br>
<i>The default value is: No</i>

<h2>Time period, sec</h2>
The amout of time between the connection checks, in seconds.<br>
It's not reccomended to set value lower then 60 seconds, it could make your WiMAX connection unworkable on unstable connections due constant restarts.<br>
<br>
<i>The defalut value is: 60</i>

<h2>Restart dead connection</h2>
When enabled, this setting allows to force reset WiMAX connection, if connection check fails with an error.<br>
It allows to keep your WiMAX modem in the active state.<br>
<br>
<i>The default value is: No</i>