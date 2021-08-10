---
title: Setup Guide
feature_text: |
  A demo of Markdown and HTML includes
feature_image: "https://picsum.photos/2560/600?image=873"
excerpt: "A demo of Markdown and HTML includes"
layout: guide
aside: True
---

> #### What you will need:
> - *n* x Raspberry Pi 4s (*n* will depend on your use case, we had 15)
> - One micro SD card for initial setup of the Pis
>   - Minimum 8GB
> - A server computer (this can be a laptop, another Pi, a desktop computer or an actual server)
>   - For any of these options, a decent storage capacity will be required (Minimum 64GB) to boot from and serve content to the client Pis
>   - Depending on your use-case you may need a lot more storage (our server has a 480GB SSD which holds all the offline educational content)
> - *n+2* ethernet cables
> - A switch (with at least *n+2* ports)
>   - This can be a gigabit switch (recommended) or a router configured to act as a switch
> - 4G/LTE Router (use as DHCP server)
> - *n* x accessories for each of the Pis
>   - Monitors, keyboards, mouses, microHDMI-to-HDMI cables, power supplies, headphones etc.

### Setting up the Client Pis
- You will need to first boot the Pis from an SD card. In order to do this, we recommend you use [Raspberry Pi Imager](https://www.raspberrypi.org/software/) to write your chosen OS ([Raspberry Pi OS](https://www.raspberrypi.org/software/operating-systems/#raspberry-pi-os-32-bit) is probably simplest) to the SD card

- Then repeat the following for each of the Raspberry Pi 4s that are going to be used as client devices:
  - Insert the SD card into the Pi and connect the power supply
  - Connect the Pi to a display with a microHDMI-to-HDMI cable. You should see the Pi booting
  - Once booted, go to the terminal (CTRL+ALT+T from the RPi-OS desktop) and type the following line: 
  
    `echo program_usb_boot_mode=1 | sudo tee -a /boot/config.txt`
  
    This adds "*program_usb_boot_mode=1*" to the end of the *config.txt* file. Now the Pi should be able to boot from a network.

  - Reboot the Raspberry Pi with `sudo reboot`
  - Once it has rebooted, check that the OTP has been programmed by running the following command in the terminal:

    `vcgencmd otp_dump | grep 17:`

    If the output is  `0x3020000a`, then you have been successful.

   - The Pi configuration is almost done. The final thing to do is to remove the `program_usb_boot_mode` line from *config.txt* (also make sure there is no blank line at the end). You can do this with any text editor (`sudo nano /boot/config.txt`, for example). 
    - Finally, shut the Raspberry Pi down (`sudo poweroff`). 


### Physical Device Setup
The Pis, Server and Router have to be connected to create a local network. This is where the Switch comes in handy. All devices should be connected as shown in the Wiring Diagram below. Do not insert the power supplies into the Pis yet. (why not?)

![WiringDiagram](WiringDiagram.png)

### Setting up the Server
We have used a relively beefy desktop computer running [Pop!\_OS](https://pop.system76.com/) (other Linux distributions should/could work).

Once you have your server PC up and running, the first step is to install `piserver`. Follow the instructiona on [piserver's GitHub page](https://github.com/raspberrypi/piserver)
\* You might need to run `sudo apt update` and `sudo apt upgrade` first

...more needed here?

...continue adding from the "Bulungula Tech Centre Guide" in the drive
