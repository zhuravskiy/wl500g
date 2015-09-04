In this menu you're able to set basic wireless settings like: Network name and encryption settings

# Index #
  * [Introduction](GUIWirelessInterface#Introduction.md)
  * [SSID](GUIWirelessInterface#SSID.md)
  * [Channel](GUIWirelessInterface#Channel.md)
    * [Channel overlapping](GUIWirelessInterface#Channel_overlapping.md)
      * [802.11N (draft)](GUIWirelessInterface#802.11N_(draft).md)
  * [Wireless Mode](GUIWirelessInterface#Wireless_Mode.md)
  * [Bandwidth](GUIWirelessInterface#Bandwidth.md)
  * [802.11n SubChannel](GUIWirelessInterface#802.11n_SubChannel.md)
  * [Authentication Method](GUIWirelessInterface#Authentication_Method.md)
  * [WPA Encryption](GUIWirelessInterface#WPA_Encryption.md)
  * [WPA Pre-Shared Key](GUIWirelessInterface#WPA_Pre-Shared_Key.md)
  * [WEP Encryption](GUIWirelessInterface#WEP_Encryption.md)
  * [Passphrase](GUIWirelessInterface#Passphrase.md)
  * [WEP Key X (10 or 26 hex digits)](GUIWirelessInterface#WEP_Key_X_(10_or_26_hex_digits).md)
  * [Key Index](GUIWirelessInterface#Key_Index.md)
  * [Network Key Rotation Interval](GUIWirelessInterface#Network_Key_Rotation_Interval.md)


---


## Introduction ##
Wireless networking is not very easy to understand when it comes to the science of wlan.
In this article I make an attempt to keep it easy, but with the handy to know facts that'll make your wireless network work.


---

## SSID ##

The SSID is the wireless network name the router will use.
Clients will identify wireless networks by their name.
Unless you want to make a [roaming network](http://en.wikipedia.org/wiki/Wireless_LAN#Roaming) or a [WDS network](http://en.wikipedia.org/wiki/Wireless_Distribution_System)
you'll need to choose a unique name preferably easy to remember.
The SSID must not exceed 32 characters.

**note: choosing your address as SSID is usually not safe. Burglars tend to break in at houses with their address as SSID.**

The SSID is also important for WPA and WPA2 encryption security since it's a part of the generated security key.
This uniqueness will protect you from "[Rainbow tables](http://en.wikipedia.org/wiki/Rainbow_table)" based attacks.

---

## Channel ##

WiFi communicates over a range of frequencies, to make it easier they are numbered for 802.11B/G/N.
Usually the best results will be achieved with the "auto" setting, this way the router will pick the best possible channel at the moment it boots.

WiFi allows a total of 14 channels. In some countries it's not allowed to use all channels though.

| **Channel** | **North America** | **Japan** | **Most of the world (e.g. Europe)** |
|:------------|:------------------|:----------|:------------------------------------|
|1            |yes                |yes        |yes                                  |
|2            |yes                |yes        |yes                                  |
|3            |yes                |yes        |yes                                  |
|4            |yes                |yes        |yes                                  |
|5            |yes                |yes        |yes                                  |
|6            |yes                |yes        |yes                                  |
|7            |yes                |yes        |yes                                  |
|8            |yes                |yes        |yes                                  |
|9            |yes                |yes        |yes                                  |
|10           |yes                |yes        |yes                                  |
|11           |yes                |yes        |yes                                  |
|12           |no                 |yes        |yes                                  |
|13           |no                 |yes        |yes                                  |
|14           |no                 |802.11b only|no                                   |

This table only shows general information, are you unsure about what channels you may use, please refer to your local authorities or search the web.

Channels must be set to a fixed number when using [WDS networking](http://en.wikipedia.org/wiki/Wireless_Distribution_System).

### Channel overlapping ###
The WiFi alliance specified a few rules when it comes to channels.
Unlike you may think, a specific channel does not represent one frequency, but a range of about 20MHz around the central frequency.
If you do the math: 20 x 14 = 280MHz which does not fit between ~2400 and ~2500 MHz.
To overcome this the WiFi alliance made the channels overlap each other:

> [http://i41.tinypic.com/nz3j85.jpg Channel overlapping](http://i42.tinypic.com/2e549x1.jpg)

In this graph you can see the overlapping of the channels.
Every channel has a lower, center and upper frequency.
The center frequency is shown by the horizontal line.

Because the frequencies are overlapping, it's not a good idea to choose a channel close to another WiFi network channel since they might interfere with each other.
Choosing a non overlapping channel will guarantee you have optimal signal quality and throughput.

Usually the best channels to choose are 1, 6 or 11 since they do not overlap each other.

> ### 802.11N (draft) ###
> 802.11N is a bit different than 802.11B/G networks since it usually uses 40MHz to enable throughputs of 300Mbit/s.
> When you want to use 20MHz only, you don't need to worry about this chapter.
> Since the specification wants us to use a maximum of ~20MHz, 802.11N will use 2 channels to get a total of 40MHz.
> When it comes to channels, this means that you can choose the first channel by picking a number out of the list between 1 and 9 (6 usually has the best results). The second channel will be assigned by the setting "802.11n SubChannel" which will choose 2 channels higher or lower than the first channel.
> Check the "802.11n SubChannel" setting instructions for more information.


---

## Wireless Mode ##

Different modes are available to choose from, recommended is "Auto" which will allow all types of 802.11.
Available modes available differ per router, but this is the list:

#### Auto ####
> Allow every mode available for your router: 802.11b/g/n
> Recommended setting!
#### 802.11g only ####
> Only allow clients supporting 802.11g (54Mbit/s)
> When you have only 802.11g clients this is probably the best setting.
> It optimizes maximum throughput as well as range.
#### Performance ####
> This is a special option for 802.11g which allows high throughputs.
> This mode usually only works with special Asus WiFi adapters supporting throughput boost functionalities.
#### 54G LRS ####
> The so called "Limited Rate Support".
> This is only needed when some 802.11b clients can't connect. So its the special compatibility mode.
> 802.11g clients are also allowed.
#### 802.11n Only ####
> Only allow clients supporting 802.11n.
> When you have only 802.11n clients this is probably the best setting.
> It optimizes maximum throughput as well as range.


---

## Bandwidth ##
This option is only available for 802.11N enabled routers.
As explained in the chapter: Channel -> Channel Overlapping -> 802.11N (draft) 802.11N is able to use the "normal" 20MHz as well as 40MHz.

The only difference apart from what channels will be used is the maximum throughput you can achieve.

20MHz will allow you to use a maximum of 155Mbit/s and uses just a single channel.
40MHz will allow speeds up to 300Mbit/s and uses 2 channels.

40MHz is recommended because it interferes less with existing networks and allows higher throughputs.


---

## 802.11n SubChannel ##
If your router is (draft) N compatible you can choose how the router will handle the second channel.

This is especially handy when you try to maneuver trough crowded WiFi hotspots to get a better signal.

When you select upper, the second channel will be 2 channels higher than the first channel specified at the "Channel" setting.

When you select lower it's just the other way around.

And when you select None the second channel will be the same as the first channel, which means you'll have only 20MHz bandwidth to use.


---

## Authentication Method ##
You can choose from several different authentication methods.
Basically this means the encryption of what you send wirelessly, and how hard it is to break into.
Lets go trough the available options:
#### Open System ####
> With this method you can use both a password or none to gain access to your network.
> It provides low level of security which is easy to hack and is not really recommended.
#### Shared Key ####
> This is pretty much the same as Open System authentication which is fairly unsafe to use.
> The Shared Key method is even less secure to use since a hacker will be able to see what's going on even easier!
> The only difference from Open System is that the Shared Key requires a password.
#### WPA-Personal ####
> This encryption provides a pretty good security.
> It's a lot harder to hack since the encryption is not linear.
> For WPA-Personal are 2 types of encryption standards available: [TKIP](http://en.wikipedia.org/wiki/Temporal_Key_Integrity_Protocol) and [AES](http://en.wikipedia.org/wiki/Advanced_Encryption_Standard).
#### WPA2-Personal ####
> The second version of WPA, and is more secure than WPA-Personal.
> The reason is because a new AES based type of encryption is added for WPA2: [CCMP](http://en.wikipedia.org/wiki/CCMP). When you choose AES as WPA2 encryption you will use this new  type.
> At this moment of writing WPA2-AES is considered safe since it requires so much calculating that a single super computer would take more than 10 years to crack the code.
> If your wireless clients support WPA2, it's HIGHLY recommended to use this protection method.
#### WPA-Auto-Personal ####
> This is a mixed mode between WPA-Personal and WPA2-Personal.
> It allows both WPA and WPA2 enabled clients to connect.\
> This authentication method requires you to choose "TKIP+AES" at "WPA Encryption".
#### WPA-Enterprise ####
> This is pretty much the same as WPA-Personal with one key difference: it requires clients to use a username and password to gain access to the wireless network.
> You need a RADIUS server for this, so for most people this is not a good option.
#### WPA2-Enterprise ####
> This is pretty much the same as WPA2-Personal with one key difference: it requires clients to use a username and password to gain access to the wireless network.
> You need a RADIUS server for this, so for most people this is not a good option.
#### Radius with 802.1x ####
> Again this is not suitable for the regular user.
> This option will use the [802.1x authentication](http://en.wikipedia.org/wiki/IEEE_802.1X) method and requires a RADIUS server.
> This method is also known as EAP.


---

## WPA Encryption ##
This sets the encryption type for WPA and WPA2 based authentication methods.

[AES](http://en.wikipedia.org/wiki/Advanced_Encryption_Standard) is considered the safest encryption method and is recommended.
[TKIP](http://en.wikipedia.org/wiki/Temporal_Key_Integrity_Protocol) is also quite safe, but still easier to crack than [AES](http://en.wikipedia.org/wiki/Advanced_Encryption_Standard).

TKIP+AES mode allows both [TKIP](http://en.wikipedia.org/wiki/Temporal_Key_Integrity_Protocol) and [AES](http://en.wikipedia.org/wiki/Advanced_Encryption_Standard) and is required for WPA-Auto-Personal authentication method.

#### 802.11N (draft) ####
> This standard requires you to use AES encryption. TKIP + 802.11N networks are not allowed.


---

## WPA Pre-Shared Key ##
This text box is required when you want to use WPA or WPA2 Personal.
You may enter 8 to a maximum of 63 characters, of course: the more the better your security is.
Also the more random your Pre-Shared Key is, the more secure.
you may use a generator to get a good key: [wpa-pskgen](http://www.kurtm.net/wpa-pskgen/)

allowed characters:
```
specials: ! " # $ % & ` ( ) * + , - . / [ ] \ ^ _ '  { } | ~
numeric: from 0 till 9 (9 included)
alpha: from a till z (z included)
capital alpha: from A till Z (Z included)
```
Sometimes the special characters do not work correctly, when this happens stick with numbers and (capital) alpha characters.


---

## WEP Encryption ##
In this box you can select which WEP encryption you want to use.

#### None ####
> It's not recommended to use this unless you want to create a free to use access point.
> Even if you protect your network with MAC authenticating it will be fairly easy to break into your network. All the data you send like: chat messages or websites you visit will be broadcasted into the open air for anyone to see.

#### WEP-64bits ####
> This protects your network by a 10 character long password.
> Remember it's quite easy to break into.

#### WEP-128bits ####
> This protects your network by a 26 character long password.
> Remember it's quite easy to break into.


---

## Passphrase ##
This is the build-in password generator for WEP keys.
Note that not every client supports pass-phrases to be filled in. Instead you must enter the generated WEP Key to gain access to your network.


---

## WEP Key X (10 or 26 hex digits) ##
You may enter 4 different WEP keys to remember, but the used key will be set by the "Key Index".

On our routers only HEX WEP keys are allowed, so you may only use these characters:
```
Numeric: 0 till 9 (9 included)
Capital alpha: A till F (F included)
```

Depending on what WEP Encryption setting you used you may only enter 10 or 26 characters.
not more, not less.


---

## Key Index ##
This setting will allow you to choose between the 4 keys you've entered.
The chosen WEP key will be used for encryption


---

## Network Key Rotation Interval ##
This option only works when you use AES encryption or TKIP+AES, only AES will be affected.
Here you can set a time in seconds before the wireless key is regenerated.
This does not mean that you need a different password to access your wireless network, but rather that it changes the generated key from your password and SSID.
Setting it for a hour or so will make your wireless network more secure but will also generate a short time of a few seconds where you can't communicate with the network.

Be aware that setting a really low value will cause you trouble with normal network usage.

Setting the value to 0 means that it never refreshes the key, this is optimal for constant streaming applications like watching streaming video's or playing online games via the wireless network.