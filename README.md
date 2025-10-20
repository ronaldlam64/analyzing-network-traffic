<p align="center">
<img src="https://i.imgur.com/3RwLv3c.png" alt="wireshark logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

The purpose of this lab is to demonstrate how to capture and analyze network traffic using Wireshark.

<h2>Environments and Technologies Used</h2>

- VMWare or Virtualbox for VM
- Wireshark
- Command Prompt

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
  

2. Open the .exe file and go through the installation wizard. You may install the other components such as Tshark and the external capture tools. I won't in this case.     Just make sure that Wireshark is selected to install. 

   <img src="https://i.imgur.com/twXzSph.png" alt="installation wizard" />

<h2>How to use</h2>

1. Open Wireshark and click Ethernet0, which is where network traffic is occuring.

   <img src="https://i.imgur.com/PX9bMsr.png" alt="opening wireshark" />

   Once Ethernet0 is opened, the application will record and display all the traffic and IP packets that is occuring at the moment and will continue to do so until stop    is clicked.

   <img src="https://i.imgur.com/k6gcXyr.png" alt="wireshark activating" />

2. The filter bar boxed in red, we can filter for a specific packet based on the parameters such as port number. I will demonstrate by filtering for packets with the       udp port 53 for DNS.

   <img src="https://i.imgur.com/p8mAjbM.png" alt="filtering for udp port 53" />

   UDP Port 53 is the protocol for DNS, which translates human-readable site addresses into ip addresses. Basically, it can be used for finding what the ip address of a    website is.

   We can see perform an nslookup for www.google.com in Command Prompt and watch what happens in Wireshark when we filter for udp.port == 53

   <img src="https://i.imgur.com/q93bGqi.png" alt="nslookup" />

   <img src="https://i.imgur.com/I6wXXM5.png" alt="udp.port == 53 running" />

   What's happening here is that:
   
   - The system may query multiple DNS servers (e.g., primary and secondary).
   - It may retry the same query if the response doesn’t come fast enough.
   - The resolver may query both IPv4 (A record) and IPv6 (AAAA record) for the same hostname.
   
     So a single nslookup can easily result in 2–6 DNS packets or more.

     In this case, my VM's ip address is 192.168.52.2 and the DNS server is 192.168.52.137. 

3. We can see that there's multiple IP addresses for www.google.com according to Command Prompt, but let's look what closely at one of the DNS packets in Wireshark.        Let's take a closer at packet number 8 in this case.

   <img src="https://i.imgur.com/XZK9vTB.png" alt="in depph view of a packet" />

   If I click the Domain Name System (response) dropdown arrow -> Answers dropwdown -> we can see the an IPV4 address for www.google.com is 142.251.15.147

4. I can test if this ip address works by typing the address in the search bar of a browser.

   <img src="https://i.imgur.com/AP9fujM.png" alt="typing ip address" />

   <img src="https://i.imgur.com/H8WvoLO.png" alt="google.com" />
