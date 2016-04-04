# osxMojo

osxMojo is a full development environment for the Mojo v3 development board (https://embeddedmicro.com/products/mojo-v3.html)

**NOTE:** For much more detailed instructions (and pictures!) check out my post here: http://alvarop.com/2016/04/mojo-v3-osx

## Installation

### Requirements
* VirtualBox and VirtualBox extension pack (https://www.virtualbox.org/wiki/Downloads)
* vagrant (brew install vagrant)
* ansible (brew install ansible)
* Xilinx ISE WebPack Installation file (http://www.xilinx.com/products/design-tools/ise-design-suite/ise-webpack.html)

### Instructions
1. Install VirtualBox, vagrant, and ansible
1. Clone this repo
1. If you already heave it, copy your *Xilinx.lic* license key file to the *roles/ise/files/* directory
1. Run `vagrant up`
	* This will setup an ubuntu VM with most prerequirements as well as create shortcuts for things
1. Login with username *vagrant* and password *vagrant*
1. Extract the Xilinx ISE Webpack installation files to the top directory on the host machine (For me it was Xilinx_ISE_DS_Lin_14.7_1015_1)
1. In the VM, run *Xilinx_ISE_DS_Lin_14.7_1015_1/xsetup* to install the Xilinx ISE tools
	* Only install the ISE Webpack
	* Make sure you set the installation path to */vagrant/opt/Xilinx*
1. Once the installation is complete, you should be able to run ISE from the desktop icon!
	* *Note:* You are now able to do `vagrant destroy` and `vagrant up` again without needing to re-install ISE, since we installed it in the /vagrant/opt directory, which is on the shared folder
