<h1>SOC-Automation-Project</h1>

<h2>Objective</h2>
The objective of this project is to start from nothing to creating a fully integrated SOAR solution incorporating Wazuh & TheHive for case management. 
<br />


<h2>Languages and Utilities Used</h2>

- <b>wireshark</b> 

<h2>Visual Representation of the SOC Automation Lab Workflow</h2>
<img src="https://i.gyazo.com/101d18e496e016840f069d9029aaa1fe.png" height="80%" width="80%" alt="tcpdump"/>

<p align="center">
Task 1: Filter the data for traffic associated with a specific IP address of "142.250.1.139" and inspect the packet as well. What is the protocol of the first packet in the list where the info column starts with the words 'Echo (ping) request'?<br/>
<img src="https://i.gyazo.com/e3fe33d87d17b64ce5286b496bbeaa69.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/23034aed27ddef04e0c2602bef6bf1b3.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/fe6e5de4595995599b69f308bbd0579c.png" height="80%" width="80%" alt="tcpdump"/>  
<br />
<br />
<p align="center">  
Task 2. Apply a basic Wireshark filter and inspect a packet for specific information <br/>
<img src="https://i.gyazo.com/cd3faa84fbcc7da2773f2e3c1ed5c6a0.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/45586ac4bf9fdb7db16b7bfd0145acd0.png" height="80%" width="80%" alt="tcpdump"/>
<br />
<br />
<p align="center">  
Task 3: You’ll use filters to analyze specific network packets based on where the packets came from or where they were sent to. You’ll explore how to select packets using either their physical Ethernet Media Access Control (MAC) address or their Internet Protocol (IP) address. 
  Enter the following filter to select traffic to or from a specific Ethernet MAC address. This filters traffic related to one MAC address, regardless of the other protocols involved: eth.addr == 42:01:ac:15:e0:02.
  After analyzing the first packet listed, what is the protocol contained in the Internet Protocol Version 4 subtree related to MAC address 42:01:ac:15:e0:02?<br/>
<img src="https://i.gyazo.com/a153ef69fbc489b79db2e183f4fbb0a5.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/98150c74ba67d390c0aaab0ac3266b85.png" height="80%" width="80%" alt="tcpdump"/>
<br />
<br />
<p align="center">  
Task 4: In this task, you’ll use filters to select and examine DNS traffic. Once you‘ve selected sample DNS traffic, you’ll drill down into the protocol to examine how the DNS packet data contains both queries (names of internet sites that are being looked up) and answers (IP addresses that are being sent back by a DNS server when a name is successfully resolved).<br/>
<img src="https://i.gyazo.com/153f4bbdca732d8490b3ec6174906415.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/336d7cb43cd64b32c31115898424d07f.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/75945508a3eb0a5fae9732e7b855f62c.png" height="80%" width="80%" alt="tcpdump"/>
<br />
<br />
<p align="center">  
Task 5: In this task, you’ll use additional filters to select and examine TCP packets. You’ll learn how to search for text that is present in payload data contained inside network packets. This will locate packets based on something such as a name or some other text that is of interest to you.<br/>
<img src="https://i.gyazo.com/d732d018ce300d62bbf095781ec4d145.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/a8dcd012f2384d0200235068f01a277a.png" height="80%" width="80%" alt="tcpdump"/>
<p align="center"> 
<br />
<br />
Task 6: Enter the following filter "curl" to select TCP packet data that contains specific text data.
<img src="https://i.gyazo.com/b22ec16b409b393b2b975e99e5320278.png" height="80%" width="80%" alt="tcpdump"/>


<br />
<br />
