This is a little how-to on how to set up an IPv6 over IPv4 tunnel via Hurricane Electric.

# Index #
  * [Introduction](#Introduction.md)
  * [HE.net IPv6 Tunnel Broeker Registration](#HE.net_IPv6_Tunnel_Broker_Registration.md)
  * [Adding an IPv6 Tunnel](#Adding_an_IPv6_Tunnel.md)
  * [Configuring the router](#Configuring_the_router.md)
    * [View the tunnel information](#View_the_tunnel_information.md)
    * [Enter the data](#Enter_the_data.md)
    * [Finished Example](#Finished_Example.md)
  * [Configuring Clients](#Configuring_Clients.md)
    * [Windows XP](#Windows_XP.md)
    * [Windows Vista or 7](#Windows_Vista_or_7.md)
    * [Linux](#Linux.md)
  * [Trying out IPv6](#Trying_out_IPv6.md)


---

# Introduction #
An IPv6 over IPv4 tunnel allows you to use IPv6 while you only have access to an IPv4 address.
  * For this to work nicely, it's handy to have a static IP-address from your internet provider.
  * In this how-to we will use HE's tunnel broker service as an example.


---

# HE.net IPv6 Tunnel Broker Registration #
Registering on the site is easy, just follow [this link](http://tunnelbroker.net/register.php).

After you filled out the form, you'll receive a generated password for your account.

When you log in with your username and password you'll see a menu on the left hand side of the site.

Clicking on "update info" will allow you to change your data, **including password.**


---

# Adding an IPv6 Tunnel #
Now looking at your tunnel broker account you can click on "Create Regular Tunnel" on the left menu.

  1. After the page is loaded up, the site will automatically find the nearest server for you.
    * It's important this information is correct for optimal speed when using IPv6.

  1. Now enter your IPv4 address in the "IPv4 endpoint" textbox.
    * Usually the "You are viewing from IP" displays your correct IPv4 address when you're not using a proxy or vpn.
  1. Just click on submit to create the tunnel, and you're done.


---

# Configuring the router #
After the tunnel creation, you will be able to see the tunnel information.
## View the tunnel information ##
  1. Click on the "Click For Main Page" link in the left menu
  1. On the main screen you will see the tunnels you own
  1. Click on the link of your new tunnel
  1. On this page you can see the information of your tunnel

Lets imagine we have the following data on the tunnel details page:

  * **IPv6 Tunnel Endpoints**
```
Server IPv4 address: 216.66.84.46
Server IPv6 address: 2001:470:1a10:11b::1/64
Client IPv6 address: 2001:470:1a10:11b::2/64
```
  * **Available DNS Resolvers**
```
Anycasted IPv6 Caching Nameserver: 2001:470:20::2
```
  * **Routed IPv6 Prefixes**
```
Routed /64: 2001:470:1a11:11b::/64
```

The other values are not required for setting up our tunnel.

## Enter the data ##
To start configuring, visit your router's web-gui: IP Config -> IPv6:
  1. At "WAN IPv6 Connection Type" choose "IP6-in-IPv4 Tunnel" or "6in4 Tunnel"
  1. At "Static IPv6 address" enter the routed IPv6 prefix without the /64
  1. At "Netsize (bits of hostpart)" enter the value: 64
    * This is the trailing /64 at the end of the routed IPv6 prefix
  1. At "Enable router advertisements" select "Yes"
  1. At "Static or local IPv6 address" enter the client IPv6 address without the /64
  1. At "Netsize (bits of hostpart)" enter the value: 64
    * This is the trailing /64 at the end of the client IPv6 address
  1. At "Remote IPv6 gateway" enter the server IPv6 address without the /64
  1. At "DNS Server" enter the anycasted IPv6 nameserver
  1. At "6in4 IPv4 remote endpoint" enter the server IPv4 address
  1. At "Tunnel MTU" enter the default value: 1280
  1. At "Tunnel TTL" enter the default value: 64

Apply the settings.

**Before the tunnel can work correctly, your modem or router needs to be pingable.**

To do this, you can either make sure your modem responds to ping requests

Or you can forward all data to your router (DMZ) and enable "Respond Ping Request from WAN" in Internet Firewall -> Basic Config.

## Finished Example ##
![http://wl500g.googlecode.com/svn/wiki/GUIIPConfigIPv6HowTo6in4.png](http://wl500g.googlecode.com/svn/wiki/GUIIPConfigIPv6HowTo6in4.png)


---

# Configuring Clients #
Before you can browse IPv6 sites you might need to restart your browser, after following the steps below.

> ## Windows XP ##
> For Windows XP you need to follow a specific procedure to enable IPv6.

> Please follow the instructions at this [kb2478747 article](http://support.microsoft.com/kb/2478747)

> After the reboot make sure IPv6 is ticked at your network card properties.

> ![http://h20000.www2.hp.com/bc/docs/support/SupportDocument/c01887303/c02230160.gif](http://h20000.www2.hp.com/bc/docs/support/SupportDocument/c01887303/c02230160.gif)

> You might need to reboot again if you had to tick it yourself.

> ## Windows Vista or 7 ##
> IPv6 is installed by default in this operating system.
    * Simply turn of and on your network card to get an address
    * Or Unplug your ethernet cable for a few seconds
    * Or if all else fails reboot your pc

> ## Linux ##
> Most Linux distributions have IPv6 support by default.

> By trying out the same tricks as for Windows Vista/7 you can obtain an IPv6 address.


---

# Trying out IPv6 #
You can simply try out if IPv6 is working by visiting these sites:
  * [ipv6.he.net](http://ipv6.he.net/) for displaying your IPv6 address
  * [test-ipv6.com](http://test-ipv6.com/) for a complete test an analysis