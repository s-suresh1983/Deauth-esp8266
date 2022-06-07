# Deauth-esp8266
esp-8266
Use it only for testing purposes on your own devices! I don't take any responsibility for what you do with this program. Please check the legal regulations in your country before using
While Wi-Fi-enabled microcontrollers like the ESP8266 do not officially support attacking Wi-Fi networks, and old SDK allows a hacker to build packets manually, thus being able to emulate many kinds of useful packets. That led CS student and chicken-in-space Stefan "Spacehuhn" Kremser to create the Wi-Fi Deauther, a program for the ESP8266 capable of several powerful Wi-Fi attacks.
The ESP8266 Deauther Program
The most useful packets the Wi-Fi Deauther can create are deauthentication and disassociation packets. These packets are often abused because they are unauthenticated, meaning anyone on a network can send them to anyone else while pretending the messages are coming from the router. When a device on the Wi-Fi network receives the packet, it immediately disconnects from the network. The Wi-Fi Deauther does this over and over, spamming connected devices with "disconnect" messages. It results in a "jamming" effect on the network as devices cannot connect fast enough to avoid being instantly kicked off.

That's not the only trick the Deauther program has up its sleeve. It's also capable of scanning for both nearby access points and connected devices, and cloning any Wi-Fi network it sees. It can also generate dozens of fake Wi-Fi networks with any names you want, monitor channels for packet traffic between devices, and do all of this from a fancy built-in web interface similar to a Wi-Fi Pineapple.
The Wi-Fi Deauther program can be run on nearly any ESP8266-based development board, including the NodeMCU, the D1 Mini, and others. These boards are cheap and can be as low as $2 to $6 depending on the manufacturer, and they allow anyone to get started hacking Wi-Fi.

While the cheapest boards are a good start, they lack a few things that make the Deauther a lot more useful. The most simple, cheap boards have no screen, no buttons or controls, and no indicators to know what's going on just by looking at the device. To control it, you'd need to log in to the web interface or buy and attach the hardware yourself.
Fortunately, Spacehuhn partnered with a board producer to create a custom ESP8266-based development board for security projects. This version of the ESP8266 features options that can be explored through a (somewhat fragile) selector switch that scrolls through menu options on an OLED display. The board allows any external antenna to be mounted on it, features an RGB LED for showing what mode the device is in, and connects either to a LiPo battery or USB power source directly.
Upon powering up the custom board, it's easy to scroll through the options to operate the board by hand. It's is a leg up on even the Raspberry Pi, which tells you almost nothing just by plugging it in without a screen. With only a battery pack, you can power the Deauther board, select a target, and launch an attack without the need for a viewing or controlling device, as is often the case with devices like the Pi Zero W.

Due to reliability issues with cheap suppliers and the numerous hardware benefits the official board offers, I highly recommend the official DSTIKE version for anyone wanting to try this project, which costs $12. There are some copycat versions available on Amazon, but they usually cost more and, again, could come from cheap suppliers. Also, while it's possible to do this with a cheap NodeMCU, you'll need a second device to log in and control the device.
Upon powering up the custom board, it's easy to scroll through the options to operate the board by hand. It's is a leg up on even the Raspberry Pi, which tells you almost nothing just by plugging it in without a screen. With only a battery pack, you can power the Deauther board, select a target, and launch an attack without the need for a viewing or controlling device, as is often the case with devices like the Pi Zero W.

Due to reliability issues with cheap suppliers and the numerous hardware benefits the official board offers, I highly recommend the official DSTIKE version for anyone wanting to try this project, which costs $12. There are some copycat versions available on Amazon, but they usually cost more and, again, could come from cheap suppliers. Also, while it's possible to do this with a cheap NodeMCU, you'll need a second device to log in and control the device.
To access it, connect to the Wi-Fi network and enter the password "deauther" to join. Then, in a browser window, you can navigate to the default IP address of 192.168.4.1 or simply type deauth.me to access the web interface the Deauther board is creating.

First, let's take a scan of the area around us. The first page you'll find yourself on is the "Scan" page, which breaks down results into a few easy to understand categories. First, there are access points. This will give you a list of every device advertising a Wi-fi network in range.
Further down the list, you'll see devices that are connected to a network, as well as which network they are connected to. You can select the "Add" button to save a particular device or network to your target list. Here, we'll select "spot 2.4 ghz" as the network we want to target.
In the "SSIDs" section, we'll be able to clone networks, create fake networks, or simply Rickroll everyone.

The top field is for specifying any fake network we want to create. This includes the SSID, or network name, whether or not the network uses WPA security, and how many networks you want to create.
If you selected an access point before, you can click "Clone Selected APs" to generate clones of the targeted network. There is also a module to generate random SSIDs, including several that are just the lines to "Never Gonna Give You Up."

we cloned the network many times, making it very hard to find the correct network.
Now, let's check out the attacks we can launch in the "Attacks" section of the menu. Here, we can see three primary kinds of attacks.

Deauth: This will attack any network in range, disconnecting it from Wi-Fi until you disable it. It's worth mentioning that you are connected to the device via Wi-Fi, and this makes it likely that you may unintentionally prevent yourself from connecting to the device to turn it off. If you find yourself disconnected and you can't get back in, you may need to unplug the board to get it to stop.
Beacon: This attack will create up to a thousand fake networks, either cloning nearby networks or creating entirely fake ones from scratch.
Probe: Here, the board will send probe requests asking for a network name that's in the list you specify. This will confuse some Wi-Fi trackers and also sometimes cause Wi-Fi attack tools to create fake networks in response to the network names contained in the probe requests.
To begin the deauthentication attack, make sure you are somewhere where the only networks that are in range are ones you have permission to attack. Once you are, click the "Start" button next to the "Deauth" attack. When you feel the Wi-Fi devices in your local area have had enough punishment, click "Stop" to end the attack.
Now that we've explored the main attacks, we can also configure the board via the "Settings" tab on the top left of the screen. Clicking on it will bring up a menu page allowing you to do things like change the name of the network used to communicate with the board, change the password, and change the channel the device broadcasts its network on.

Here, you'll also find an option to create a "Hidden" network, which might seem more stealthy to connect to. In fact, any device you connect to a hidden network will start calling out that network name any time the Wi-Fi is left on, making your phone more trackable.

The reasons devices that have connected to a hidden network always call for them is because they know the station is not broadcasting its network name, so it's up to your device to always be asking if it is nearby.

You can customize settings as much as you like here, but be careful not to disable the Wi-Fi portal and the serial connection at the same time. Doing so will leave you with no way to communicate with the board, so make sure you leave at least one enabled to allow you to get back in.

Once you update your password and the name of your command-and-control Wi-Fi network, you're ready to use the Wi-Fi Deauther anywhere, from any device. After making any changes to the menu or any other settings, make sure to press "Save" and "Reload" to apply the changes you made.

Microcontrollers Are Cheap, Efficient Cyber Weapons
The Raspberry Pi was revolutionary in giving access to powerful hacking tools to anyone who can afford a $35 board. With the Wi-Fi Deauther board, the boundaries of what can be done with low-cost Wi-Fi hardware has been pushed even further than before.

While microcontrollers don't offer a full operating system to work with like a Raspberry Pi, the powerful attacks they're capable of on their own make them more than worth checking out. While the Wi-Fi Deauther board can't capture the numerous WPA handshakes it generates from nearby networks while in operation by itself, it's a perfect companion tool for capturing WPA handshakes in Kali for later cracking.

