# Mind The Gap!
## Leveraging gaps in cross-platform security solutions on MacOS/Linux systems
## [DEF CON 27 workshop](https://defcon.org/html/defcon-27/dc-27-workshops.html) 
Unix and Unix-like systems such as Linux and MacOS have a strong reputation for security and reliability. MacOS, for example, comes with many restrictions such as the usage of an App Store to prevent malicious code being installed. However, we have found that since these *nix systems are the minority platform for many software packages and security platforms, it rarely gets the same attention from security vendors as Windows. This workshop will teach you to exploit that lack of attention from software like Microsoft Office and security platforms like leading EDR solutions to break in and out of a protected *nix estate.

We will walk you through how to use open source tools, both unmodified and customized, can be used to take advantage of the difference in capability, e.g., script detection, between Windows and non-Windows platforms like *nix. We will show you how to map out an environment, how to gain code execution in multiple ways, grab credentials, find files, collect screenshots and webcam shots and exfiltrate the loot while remaining undetected.

The key takeaway is that despite the myriad of operating system security features present in MacOS and Linux, and the addition of EDR, protected MacOS or Linux environments can still be compromised by a diligent attacker using open source tooling. This workshop will show you how!

[Unfortunately we cannot provide an EDR system for you to play with, so please bring your own or practice the techniques without that particular opponent.]

## Layout

* **slides/** - Slides for the workshop
* **tools/** - Tools used during the workshop
* **templates/** - A VBA macro template used during the workshop

## Tool Installation 

For this workshop, we recommended using [Kali Linux](https://www.offensive-security.com/kali-linux-vm-vmware-virtualbox-image-download/) for running the tools.

1. Git clone this repository: `git clone https://github.com/digitalshadows/mindthegap.git`
2. Enter the project directory: `cd mindthegap/tools`
3. Initialize and update the submodules: `git submodule update --init --recursive`

### Pupy installation

* Install the necessary dependencies: `sudo apt install -y libssl1.0-dev libffi-dev python-dev python-pip build-essential swig tcpdump python-virtualenv`
* Create your pupy workspace: `python create-workspace.py -DG pupyws`
* The version of scapy that pupy depends on won't built correctly, so you'll need to install a later version: `sudo -H pip install scapy==2.4.3rc4` or `pip install --pre scapy`

### Empire installation
* Install the necessary dependencies: `sudo ./Empire/install.sh`
* Start Empire `./empire`

### EggShell installation
* Start EggShell: `./eggshell.py`

### EvilOSX installation
* Install the dependencies: `sudo -H pip3 install -r requirements.txt`
* Start EvilOSX: `python3 start.py --cli --port 1337`
