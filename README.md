# Contingency-for-ChromeOS
# Work In Progress. TigerVNC Install Needs Fix.
A set of open-source network security tools operating on a ChromeOS Linux Development Kit.

Updating Linux:

    sudo apt update
    sudo apt upgrade

Enter Y to accept installation.

Installing Packet Monitoring Tools:

Install tcpdump.

    sudo apt install tcpdump

Enter Y to accept installation.

A window will appear asking if you'd like to allow non-super users to capture packets.

Select 'no' to prevent potential security risks.
Select 'yes' for open-source network traffic.

Run tcpdump

    sudo tcpdump -i eth0

End tcpdump using CTRL + C

Install wireshark.

    sudo apt install wireshark

Enter Y to accept installation

Open Wireshark.

    wireshark

Install tshark.

    sudo apt install tshark

Run tshark.

    sudo tshark -i eth0

If you did not allow non-super users to capture packets, you will not have permission to capture packets on any network interface.

Reconfigure Wireshark to enable the sufficient permissions.

    sudo dpkg-reconfigure wireshark-common

Select 'yes' in re-enable non-super user permissions.

Add users with usermod. 

    sudo usermod -a -G wireshark 'yourusername'

End tshark using CTRL + C

Installing Virtual Network Computers:

Install RealVNC.

Visit the link below and download the RealVNC Server DEB package for Linux.

    www.realvnc.com/en/connect/download/vnc/linux

Copy 'VNC-Server-7.10.0-Linux-x64.deb' from its original location.

Paste 'VNC-Server-7.10.0-Linux-x64.deb' to the new directory located within your computer's main Linux folder.

Return to your Linux terminal and install the DEB package.

    sudo dpkg -i VNC-Server-7.10.0-Linux-x64.deb
    
Open RealVNC

    vncserver-x11

Installing TigerVNC

Check the codename of your Ubuntu release.

    cat /etc/os-release | grep VERSION=

Install nano

    sudo apt install nano

Enable Universe Repository

    sudo nano /etc/apt/sources.list

Remove the first line and add these two lines to the nano file. Replace 'codename' with the codename of your Ubuntu release.

    deb http://archive.ubuntu.com/ubuntu 'codename' universe
    deb-src http://archive.ubuntu.com/ubuntu 'codename' universe

Save the file with CTRL + S
Exit the file with CTRL + X
Update package lists.

    sudo apt update
    sudo apt upgrade

