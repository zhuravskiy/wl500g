# Index #
  * [Introduction](GUIWirelessAccessControl#Introduction.md)
  * [MAC Access Mode](GUIWirelessAccessControl#MAC_Access_Mode.md)
  * [Access Control List](GUIWirelessAccessControl#Access_Control_List.md)


---


# Introduction #

In this page you may enter MAC addresses (wireless only) to allow or to block.

This technique is usually used for safety of the wireless network, yet it's easy to get around this by changing the MAC address of the wireless card of the client.


---

## MAC Access Mode ##

  * Disable: The Access Control List won't be used
  * Accept: Only the MAC addresses in the list are allowed to connect, others will be blocked.
  * Reject: All MAC addresses are allowed to connect except the listed MAC addresses


---


## Access Control List ##

The MAC address here does not contain colons (:) or dashes (-).

example: 001122334455

Comment is optional, and might be handy for remembering the allowed clients.