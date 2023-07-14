# Install OpenWrt on your Atlas Media Router

The Iffy Books router challenge is complete! We have a working build of OpenWrt that you can install on the Atlas Media routers we've been hacking away at for the past few months! Retry and Jim are sharing the prize, which we'll award at [Router Hack Day III](https://iffybooks.net/event/router-hack-day-3/) on Saturday, July 29th. We should also thank Anthony, who helped with initial research and did a great job spreading the word about the project.

This post will show you how to install Retry's build of OpenWrt on your Atlas Media AC1200 router (actually a rebranded Tenda FH1205 router). This project doesn't require any soldering, but you will need to disassemble the router's case and connect a couple wires to the board.

If you're interested in soldering wires to the router's serial pinout to access the serial shell, check out our blog post [Notes for Router Hack Day II](https://iffybooks.net/router-hack-day-2/). That post will also get you started on decompressing the router's stock firmware.

For background info and instructions on gaining telnet access using the router's stock firmware, check out Jim's [Challenge Router Progress Report](https://iffybooks.net/challenge-router-progress/). For hardware specs and manuals, check out [the event page for Router Hack Day I](https://iffybooks.net/event/router-hack-day/).

## Getting started

❏ Download the OpenWrt firmware from the following URL:
https://iffybooks.net/AtlasMediaOpenWrt.trx

❏ Turn off your wi-fi.

<img title="" src="./images/6ab034c20d4e423a0ad821d0add65f429a81a49b.png" alt="Screenshot from 2023-07-13 13-09-42.png" width="327" data-align="center">

❏ Connect the router to your computer with an ethernet cable and power it on.

<img title="" src="./images/3383f7bd8cb24d18522ed908b2102ba3c030da67.png" alt="IMG_6935.png" width="295" data-align="center">

❏ Give yourself a static IP address.

Ubuntu: 

<img title="" src="images/2d2d5fcc9465988903a35a781f4ee3661f2ee4ce.png" alt="Screenshot from 2023-07-13 13-12-10.png" width="539" data-align="center">

<img title="" src="images/f62d397e52ca420cd41f291415a8505750a1edb5.png" alt="Screenshot from 2023-07-13 13-12-39.png" width="436" data-align="center">

<img title="" src="images/7e7faccd2b54ea7ad249495c45472d8a9a7d6003.png" alt="Screenshot from 2023-07-13 13-13-15.png" width="439" data-align="center">

<div style="page-break-after: always;"></div>

macOS: 
Windows: 

❏ Connect the port end of your alligator clip to the GND pin on your USB serial interface.

<img title="" src="images/cb97a01b3b665000cade14f0dd88761e9ff51611.png" alt="IMG_6947.png" width="281" data-align="center">

❏ Attach the port end of a port-to-plug jumper wire to the USB serial interface’s Tx pin.

<img title="" src="images/7bf52165ad84f4e4d529e181b3cb09ae8c584e69.png" alt="IMG_6956.png" width="402" data-align="center">

❏ Disconnect the power cable and Ethernet from the router.

❏ Find the screw on the bottom of the router and unscrew it. Remove the base.

<img title="" src="images/67b751c9dd8e9df0b37f5306156c9d3a097ca14a.png" alt="IMG_6963.png" width="255" data-align="center">

❏ With the thicker side of the router facing left, pry off the front panel of the case. It's easiest to start at the corner on the narrow end.

<img title="" src="images/a81bee42b9253d673ef24df8b152619d26537e0a.png" alt="IMG_6984.png" width="445" data-align="center">

Here's what the router looks like inside:

<img title="" src="images/6fe21cb379e3f991c3312e1282b87d468a0cca26.png" alt="IMG_6990.png" width="386" data-align="center">

<img title="" src="images/048f922c1a3e162eb3d2bace5a2368f4757e342b.png" alt="IMG_6998.png" width="354" data-align="center">

❏ Run the following command to install minicom:

sudo apt-get install minicom

<img title="" src="images/b20d54055a06cdf021eaa8d612edd8ccebf571c4.png" alt="Screenshot from 2023-07-13 13-22-15.png" width="489" data-align="center">

❏ Attach your USB serial interface to your computer.

<img title="" src="images/b0ec3f9d7c17974cf0eedcc814701b89bade96d9.png" alt="IMG_7002.png" width="499" data-align="center">

❏ Open a terminal window and run the following command:

minicom -D /dev/ttyUSB0 -c on

<img title="" src="images/31188b4c28e1c32c2273e2236be5da47c3badd3b.png" alt="Screenshot from 2023-07-13 13-24-01.png" width="513" data-align="center">

❏ Next you'll test your USB serial adapter. Touch the plug end of your Tx jumper wire to the Rx pin, then type a few characters in the minicom window. If the characters appear onscreen, your USB serial interface is working.

<img title="" src="images/582df64a24bd07fd487ca76c0da71ea30b528c47.png" alt="Screenshot from 2023-07-13 13-24-51.png" width="495" data-align="center">

❏ Reconnect the ethernet cable to your router.

❏ Attach the alligator clip from your USB serial interface to the exposed metal on one (or both) of the router's external buttons.

<img title="" src="images/06569221e3972a22b7316c57b5a7c375205a512a.png" alt="IMG_7019__.png" width="359" data-align="center">

<img title="" src="images/293b270e4f1c05ea8c294a7ad60fe2133ad79c02.png" alt="IMG_7011.png" width="281" data-align="center">

❏ Touch the plug end your Tx jumper wire to the Rx pin indicated in the photo below. Hold it there firmly for the next step.

<img title="" src="images/262b6ef61a6e2933b5b7c6536a51bf59b7c202c7.png" alt="IMG_7020.png" width="329" data-align="center">

❏ Make sure your minicom terminal window is open. Plug in your router and immediately press ctrl+C on your keyboard repeatedly.

❏ Open your browser and go to the following address: http://192.168.1.1

If you're in CFE mode, you'll see a page like the one below. If not, skip back to the previous step and try again.

<img title="" src="images/24860dc112ca8ce392b8841e6a8bcab43ecdf7c4.png" alt="Screenshot from 2023-07-13 13-31-47.png" width="651" data-align="center">

❏ Click **Browse ...** and select the firmware file, **AtlasMediaOpenWrt.trx**.

❏ Click **Upload** to start uploading the file.

<img title="" src="images/7e73de9f6d2082d4b7fc8e6b3b344bc3fbeff9d7.png" alt="Screenshot from 2023-07-13 13-32-05.png" width="632" data-align="center">

❏ When you see the page below, it means your firmware has been uploaded successfully.

<img title="" src="images/8e7c19066365ef0fc58d09460905f39dbadddfb0.png" alt="Screenshot from 2023-07-13 13-32-46.png" width="641" data-align="center">

❏ Wait a minute or two for OpenWrt to finish setting up, then go the following address in your browser:
http://192.168.1.1

<img title="" src="images/2d03574321a0b618ba1b850e16371c83b3e628cd.png" alt="Screenshot from 2023-07-13 13-35-17.png" width="651" data-align="center">

❏ There's isn't a password set by default. Press enter to log in.

❏ Set a new password.

<img title="" src="images/6de9ab2666529d68a3c30a699e372956c9434236.png" alt="Screenshot from 2023-07-13 13-35-25.png" width="644" data-align="center">

❏ Change your router's local IP address to avoid conflicts.
[...]

❏ Before reassembling your router's case, you may want to drill holes in it to provide access to the ground and Rx pins in case you want to re-flash the firmware later.

❏ Remove the alligator clip from the router.

❏ Snap the case back together. (You may want to disconnect power while you do this.)

❏ Screw on the router's base.

###########

- Give Your Router a Unique IP address on the LAN:

https://openwrt.org/docs/guide-user/network/openwrt_as_routerdevice

Change the IP address to 192.168.1.X, where X is a number <= 255, but not 1.

- Connect an ethernet cable from the internet to your router

- Check your internet connection

ssh root@192.168.1.10

- Update the package manager

opkg update

- Open the OpenWrt admin panel and go to System > Software 
