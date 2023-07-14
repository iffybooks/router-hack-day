# 

❏ Download the OpenWrt firmware from the following URL:
https://iffybooks.net/AtlasMediaOpenWrt.trx

❏ Turn off your wi-fi.

<img src="images/6ab034c20d4e423a0ad821d0add65f429a81a49b.png" title="" alt="Screenshot from 2023-07-13 13-09-42.png" width="327">

 

❏ Connect the router to your computer with an ethernet cable and power it on.

<img src="images/3383f7bd8cb24d18522ed908b2102ba3c030da67.png" title="" alt="IMG_6935.png" width="295">



❏ Give yourself a static IP address.

Ubuntu: 

![Screenshot from 2023-07-13 13-12-10.png](2d2d5fcc9465988903a35a781f4ee3661f2ee4ce.png)

![Screenshot from 2023-07-13 13-12-39.png](f62d397e52ca420cd41f291415a8505750a1edb5.png)

![Screenshot from 2023-07-13 13-13-15.png](7e7faccd2b54ea7ad249495c45472d8a9a7d6003.png)




macOS: 
Windows: 

❏ Connect the port end of your alligator clip to the GND pin on your USB serial interface.

![IMG_6947.png](cb97a01b3b665000cade14f0dd88761e9ff51611.png)



❏ Attach the port end of a port-to-plug jumper wire to the USB serial interface’s Tx pin.

![IMG_6956.png](7bf52165ad84f4e4d529e181b3cb09ae8c584e69.png)



❏ Disconnect the power cable and Ethernet from the router.

❏ Find the screw on the bottom of the router and unscrew it. Remove the base.

![IMG_6963.png](67b751c9dd8e9df0b37f5306156c9d3a097ca14a.png)





❏ With the thicker side of the router facing left, pry off the front panel of the case. It's easiest to start at the corner on the narrow end.

![IMG_6984.png](a81bee42b9253d673ef24df8b152619d26537e0a.png)

![IMG_6990.png](6fe21cb379e3f991c3312e1282b87d468a0cca26.png)

![IMG_6998.png](048f922c1a3e162eb3d2bace5a2368f4757e342b.png)



❏ Run the following command to install minicom:

sudo apt-get install minicom

![Screenshot from 2023-07-13 13-22-15.png](b20d54055a06cdf021eaa8d612edd8ccebf571c4.png)



❏ Attach your USB serial interface to your computer.

![IMG_7002.png](b0ec3f9d7c17974cf0eedcc814701b89bade96d9.png)



❏ Open a terminal window and run the following command:

minicom -D /dev/ttyUSB0 -c on

![Screenshot from 2023-07-13 13-24-01.png](31188b4c28e1c32c2273e2236be5da47c3badd3b.png)



❏ Next you'll test your USB serial adapter. Touch the plug end of your Tx jumper wire to the Rx pin, then type a few characters in the minicom window. If the characters appear onscreen, your USB serial interface is working.

![Screenshot from 2023-07-13 13-24-51.png](582df64a24bd07fd487ca76c0da71ea30b528c47.png)





❏ Reconnect the ethernet cable to your router.



❏ Attach the alligator clip from your USB serial interface to the exposed metal on one (or both) of the router's external buttons.

![IMG_7019__.png](06569221e3972a22b7316c57b5a7c375205a512a.png)

![IMG_7011.png](293b270e4f1c05ea8c294a7ad60fe2133ad79c02.png)





❏ Touch the plug end your Tx jumper wire to the Rx pin indicated in the photo below. Hold it there firmly for the next step.

![IMG_7020.png](262b6ef61a6e2933b5b7c6536a51bf59b7c202c7.png)



❏ Make sure your minicom terminal window is open. Plug in your router and immediately press ctrl+C on your keyboard repeatedly.

❏ Open your browser and go to the following address: http://192.168.1.1

If you're in CFE mode, you'll see a page like the one below. If not, skip back to the previous step and try again.

![Screenshot from 2023-07-13 13-31-47.png](24860dc112ca8ce392b8841e6a8bcab43ecdf7c4.png)

❏ Click **Browse ...** and select the firmware file, **AtlasMediaOpenWrt.trx**.

❏ Click **Upload** to start uploading the file.

![Screenshot from 2023-07-13 13-32-05.png](7e73de9f6d2082d4b7fc8e6b3b344bc3fbeff9d7.png)

❏ When you see the page below, it means your firmware has been uploaded successfully.

![Screenshot from 2023-07-13 13-32-46.png](8e7c19066365ef0fc58d09460905f39dbadddfb0.png)



❏ Wait a minute or two for OpenWrt to finish setting up, then go the following address in your browser:
http://192.168.1.1

![Screenshot from 2023-07-13 13-35-17.png](2d03574321a0b618ba1b850e16371c83b3e628cd.png)

❏ There's isn't a password set by default. Press enter to log in.

❏ Set a new password.

![Screenshot from 2023-07-13 13-35-25.png](6de9ab2666529d68a3c30a699e372956c9434236.png)



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
