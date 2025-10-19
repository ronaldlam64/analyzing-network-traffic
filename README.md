<p align="center">
<img src="https://i.imgur.com/3RwLv3c.png" alt="wireshark logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

The purpose of this lab is to demonstrate how to capture and analyze network traffic using Wireshark.

<h2>Environments and Technologies Used</h2>

- VMWare or Virtualbox for VM
- Wireshark
- Remote Desktop

<h2>Operating System Used</h2>

- Windows 10 Enterprise Edition

<h2>Prerequisities</h2>

- **I will not show how to install and setup VMWare or Virtualbox running the Windows 10/11 Pro or Enterprise edition. Here are the links on how to install and setup this up.**
- <a href="https://knowledge.broadcom.com/external/article/344595/downloading-and-installing-vmware-workst.html" target="_blank">VMWare Download link</a>
- <a href="https://www.virtualbox.org/wiki/Downloads" target="_blank">Virtualbox Download link</a>
- <a href="https://drive.google.com/file/d/1gyYBmOUnoNJiZQi3vncEkILpBNRA1fHU/view?usp=sharing" target="_blank">Windows 10 Pro Download link</a>
- <a href="https://drive.google.com/drive/folders/1hHvZopC54WQNf1yKBCvyFgn1ZHj8w4Qc?usp=sharing" target="_blank">Windows 10 Enterprise Download link</a>

<h2>Installation steps</h2>

1. First download Wireshark using the following link: https://www.wireshark.org/

   <img src="https://i.imgur.com/3RwLv3c.png" alt="wireshark download link"/>

   Make sure to download the correct installer based on your operating system. In this case, since I'm using Windows 10 Enterprise, I'll download Windows x64 (not Arm64)

   <img src="https://i.imgur.com/5Ykwz63.png" alt="correct installer" />
  

2. Open the .exe file and go through the installation wizard. You may install the other components such as Tshark and the external capture tools. I won't in this case. Just make sure that Wireshark is selected to install. 

   <img src="https://i.imgur.com/twXzSph.png" alt="installation wizard" />

3. Open Wireshark and click Ethernet0, which is where network traffic is occuring.

   <img src="https://i.imgur.com/PX9bMsr.png" alt="opening wireshark" />

   Once Ethernet0 is opened, the application will record and display all the traffic that is occuring at the moment and will continue to do so until stop is clicked.

   <img src="https://i.imgur.com/k6gcXyr.png" alt="wireshark activating" />
