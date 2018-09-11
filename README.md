# xyPlatform
## Project
This xyPlatform project contains Vagrant and Docker configuration files for a few general purpose operating systems that can be deployed locally in desktop environment or in the cloud. These VMs can be used for development and testing.

Many develop and test automation features provided by the Ubuntu OS are accounted for and can be used directly. Namely:
* ssh
* RDP (rdesktop)
* screen capture (import)
* video capture (ffmpeg)
* concurrent users (xvfb)
* node.js (node 8.11.1)
* google-chrome browser
* tensorflow board (port 6006)
* and many more...

### The operating systems include:
* Ubuntu 16.04 LTS, vagrant and docker
* Ubuntu 18.04 LTS, vagrant and docker
* Windows 10, vagrant only
* Windows 7, vagrant only

The Ubuntu systems have corresponding Vagrant and Docker configuration files, therefore one can develop and test at the local Ubuntu system and expect it to run at the cloud Docker container with no or minimal additional configuration.

## Benefits
1. The deployment process have been automated to remove the technical pains and nuances for end-users.
2. The configurations are captured in source code form for repeatability and future improvements.
3. It can be deployed anywhere that has git access to this git repo.
4. Easy repeatable deployment of multiple systems (i.e., deploy 32 windows systems and destroy them after use).
5. And many more...

## Prerequisites

### Local hosting system:
```
Windows 10 with reasonable RAM (16G+) and HD space (500G+)
* Vagrant 2.1.1 and up
* Vagrant Plugins
    * vagrant-vbguest
    * vagrant-ca-certificates
    * vagrant-proxyconf
    * vagrant-timezone
    * vagrant-winrm
* VirtualBox 5.2.10 and up
```

### Cloud hosting system:
```
Any Linux system that supports Docker
```

### Projects directory configuration:
The project path of $HOME/Projects and ~/Projects are used through out, and is shared into VMs via Vagrant and Docker configurations, therefore a main diretory called Projects should be created under the user's home directory, and this and other related projects should be checkout into the Projects directory. The main benefit of sharing the Projects directory with the VMs is easy exchange of code between the host and VMs.

## Deploy VMs

### Ubuntu 18.04
#### bring up and shell login
```
CMD> cd ~/Projects/xyPlatform/lubuntu
CMD> vagrant up l1804Base
CMD> vagrant reload l1804Base (reload is only needed the first time)
CMD> vagrant ssh l1804Base
```
#### gui login
vagrant/vagrant

### Ubuntu 16.04
Same as ubuntu 18.04 except change hostname with l1604Base

### Windows 10
#### bring up and shell login
```
CMD> cd ~/Projects/xyPlatform/windows10
CMD> vagrant up win10Base
CMD> vagrant reload win10Base (reload is only needed the first time)
CMD> vagrant ssh win10Base
```
#### gui login
IEUser/Passw0rd!

### Windows 7
Same as Windows 10 except in Windows7 directory and change hostname to win7Base

