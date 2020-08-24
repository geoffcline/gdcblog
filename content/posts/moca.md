---
title: "In The Absence of A Home Ethernet Wiring"
date: 2020-08-23T23:22:08Z
draft: false
---

My psychiatrist described my habit of showing up at resedential construction sites and demanding they install a whole home ethernet networks as "unhealthy" and "unproductive". Luckily, I avoided having to process that commend, because I found out you can repurpose common coaxial (cable television) cabling as an ethernet network using Moca. 

For example, you have a cable modem that supports moca in your living room. You have a home office, and would like to connect your desktop there to the internet with a wired ethernet connection. However, it's impractical to run an ethernet cable. Check and see if there is a coaxial (e.g., cable) outlets in the office. If so, you can add a moca adapter there. Then, connect your desktop to the moca adapter with ethernet. The moca adapter creates a connection over the coax cable back to the cable modem, similar to a long ethernet cable. You now have lots of bandwith and low latency in your office, without having to run another cable!

From another perspective, this allows your to have a "second cable modem" in your home, where you can attach devices at wired speeds and avoid the inconsistency of wifi. 

The latest moca adapters support speeds upto 1 gigabit. I persoanlly see total latency of ~10ms on my home setup, so that isn't a problem. 

Overall, we are going to create a 'moca bridge' between two devices in your home. This is equivalent to connecting them via ethernet, but it's going to use a coaxial cable that is already existing in your home. 

The bridge is often between your cable modem and a secondary moca device. However, your cable modem must support moca. Most new Comcast Xfinity modems do. If your modem doesn't support it, you can simply purchase 2x moca adapters, and use one at both ends. In other words, some cable modems have a moca adapter built in, saving you some money. 

## Check your Coax

Obviously, we need coaxial connections in both locations. The cable modem logically already has one, a "primary" cable. The lcoation where you are installing the moca adapter (e.g., home office) will be supplied by a "secondary" cable. 

The next step is to trace the priamary and secondary cables back to the cable box. In some homes, this is outdoors in a grey plastic box. You can identify it because it will have a tangled mess of thick coaxial cables insidse. In some apartments, it's hidden indoors. Check closets and behind panels. I found mine behind a blind outlet faceplate (e.g., plastic outlet cover). 

Now, you must confirm that both the primary and seconday cables are connected. 

There is one cable coming in from your internet/cable provider. This incoming cable is (usually) connected to a splitter. You can identify the primary cable by looking at the label on the existing splitter. 

The goal here is to confirm that (1) both the primary and secondary cables are connected to the output of the splitter, (2) the spliter is connected to the incoming cable, and (3) the splitter is appropriate. 

For both simplicity and optimal performance, I got a 2-way (e.g, 1 input, 2 outputs) splitter from Home Depot. I connected the primary and secondary cables up to the input.

What you don't want is something like a 6-way splitter where you aren't using 4 of the connections. 

If your cables aren't labeled, sadly you will have to use trial/error to find the correct connection. Change the cables connected to the splitter until the cable connection light illuminates on the target device.

I reccommend investigating your coaxial cable sitatuion before purchasing the moca modem. 

## Check your Modem

Login to the web interface of your modem. You can usually find instructions (e.g., ip address, default username/password) written on the bottom/back of the device. Login and browse around pages such as "status", "network interfaces", "LAN", etc, and see if there is a MOCA page, and an option to enable it. It was relatively easy to find on my Comcast Xfinity Xfi modem/router. 

Note, if you have a seperate cable modem and wifi router, you do not have a moca adapter integrated into the cable modem. 

If you don't have an integrated moca adapter, no problem. Just order two. 

## Setup Primary Connection

### Integrated Moca Adapter with Router

Double check it is turned on in your router settings (term modem vs router). 

### Seperate Moca Adapter 

Attach a 2 way splitter to the cable that was formerly supplying your cable modem. Reattach the cable modem and a new moca adapter. Connect the moca adapter to your router using an ethernet cable.  

## Setup Secondary Connection

Attach the second moca adadpter to the coaxial cable in the secondary location (e.g., home office). There is no setup of the moca adapter itself, it's comparable to an ethernet connection.  Now, you can connect an ethernet device (e.g., desktop computer, smart tv) to the moca adapter and enjoy a high speed connection. 

Some moca adapters have an integrated switch, so you can connect multiple devices. Otherwise, you can connect your own switch. 

## Conclusion

- discussion of my setup?
- link to products
