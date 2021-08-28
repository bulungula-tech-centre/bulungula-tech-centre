# Bulungula Tech Centre
This repository contains the instructions to replicate the low-cost, low-power computer lab we built at the Bulungula College, a school in rural South Africa. Our goal was to use free and open-source software to make this solution as accessible as possible. Please see our [`Webite`](https://bulungula-tech-centre.github.io/) for more about the project's motivation and context. If you have any technical questions, please raise them in the [`Issues`](https://github.com/bulungula-tech-centre/bulungula-tech-centre.github.io/issues) section. 

## Overview

### Power and Internet Constraints
Our solution is targeted at rural schools which may have significant electricity and internet constrains. In our case, the school was completly off grid and relied on a solar-panel installation for electricity. The school also had limited access to the internet. The only way to get online was to use an LTE router which, in such a remote area, can be unreliable and expensive. 

To operate within the power constraint, our solution proposes using Raspberry Pis instead of fully fledged PCs. Raspberry Pis are relativly inexpensive and consume very little power. This makes them the perfect solution for the off-grid setting. To adress the internet constraint, we propose an offline content sharing server such that learning materials can be downloaded from the internet once and then shared indefinitely on the local network.

### Client-Server Architecture
To facilitate easy administration and maintainance of the computer lab we used a client-server architecture whereby there is one central server-PC which controls all of the client PCs. This setup is useful because it allows one to control all of the cleint PCs from the central PC. This makes it easy to push software and security updates to all of the client PCs. Moreover, the server stores the shared content on the local network for the clients.

Another benefit of the client-server architecture is that we can network-boot the Raspberry Pis from the server. So, instead of attaching storage and an OS to each indevidual Raspberry Pi we can serve the operating system to all the Pis over the local network. The file system is stored and shared on the central server which means that users can login into their account on any of the client PCs and have access to their files. This kind of networked solution can cost thousands of dollars if you use enterprise software but thankfully there is an incredible free and open-source solution developed by the Raspberry Pi Foundation called [`Piserver`](https://github.com/raspberrypi/piserver) which we used for this project. 

### Offline Digital Learning Platform
To give the students using the computer lab the best digital learning experience possible we propose using [`Kolibri`](https://learningequality.org/kolibri/), an incredible free and open-source Offline Digital Learning Platform developed by the Learning Equality Foundation. `Kolibri` makes it possible for teachers to create digital lessons for their students in the computer centre.

### Remote Troubleshooting and Support
Another very important consideration when developing a solution for a remote location such as a school in rural South Africa is how to fix the system in the event that something goes wrong. While it is important that people on-site receive sufficient training to be able to address most issues on-site, it is important to have a remote support plan in place to recover the system from unforseen issues. To facilitate this we propose a solution which uses a free and open-source VPN solution to securly connect to the computers local network from anywhere in the world. This makes it possible for an expert to offer remote support via SSH or remote desktop if neccesary. 

---

## Setup Guide
You can find our setup guid [here](https://bulungula-tech-centre.github.io/setup/)

### Troubleshooting
You can find a list of the most common issues and how to resolve them [here](https://github.com/bulungula-tech-centre/bulungula-tech-centre.github.io/blob/main/TROUBLESHOOTING.md)
