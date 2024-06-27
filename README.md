<h1>SOC-Automation-Project</h1>

<h2>Objective</h2>
The objective of this project is to start from nothing to creating a fully integrated SOAR solution incorporating Wazuh & TheHive for case management.
The SOC Automation Project aims to enhance cybersecurity operations by automating threat detection, incident response, and security monitoring processes. 
<br />

<h2>Visual Representation of the SOC Automation Lab Workflow</h2>
<img src="https://i.gyazo.com/101d18e496e016840f069d9029aaa1fe.png" height="80%" width="80%" alt="tcpdump"/>

<h2>Tools Used</h2>
-<b>Windows VM: Ensured coverage and monitoring in Windows environments.</b><br/>
-<b>Sysmon: Provided detailed monitoring of system activity.</b>
-<b>Wazuh: Open-source security monitoring for event analysis and compliance management.</b>
-<b>TheHive: For case management and collaboration in incident response.</b>
-<b>DigitalOcean: Cloud infrastructure provider for hosting the environment.</b>
-<b>Mimikatz: Security tool used for testing and validating detection capabilities.</b>
-<b>OSSEC: Integrated for log analysis and intrusion detection.</b>
-<b>Shuffle: Automation tool for integrating workflows and triggering responses.</b>
-<b>VirusTotal: API integration for automated threat intelligence and reputation checks.</b>
-<b>Windows VM: For ensuring coverage and monitoring in Windows environments.</b>
-<b>Wazuh: Open-source security monitoring for event analysis and compliance management.</b>

<h2>Steps</h2>
-Installing and implementing a cloud environment (Digital Ocean)

-Configure a firewall on a cloud environment
<img src="https://i.gyazo.com/7c2ed0d6f30cd93c356d0c13a3b615bc.png" height="80%" width="80%" alt="tcpdump"/>

-Implement firewall configurations for both Wazzuh & theHive servers.

-SSH into our virtual machine and install Wazzuh including all prerequisites
<img src="https://i.gyazo.com/fc455d8ae843a3129bfb03abe25bccff.png" height="80%" width="80%" alt="tcpdump"/>

-SSH into our virtual machine and install theHive including all prerequisites
<img src="https://i.gyazo.com/65f36e61e7749936d993d2bde0442e0f.png" height="80%" width="80%" alt="tcpdump"/>

Configure all files for Wazzuh and theHive via virtual machine

Once both Wazzuh and theHive have been configured on your server, they should both appear active and running on your host ip address:
<img src="https://i.gyazo.com/5f4f0a0941def2c95cc76e27cf79897b.png" height="80%" width="80%" alt="tcpdump"/>

Add an agent to your Wazuh manager:
<img src="https://i.gyazo.com/52fe09d937f2cdb0a07ac7c9462e90ab.png" height="80%" width="80%" alt="tcpdump"/>

Install mimikatz

Configure osec configurations to ingest sysmon logs

Check Wazuh dashboard to see if it successfully archived any mimikatz events: 
<img src="https://i.gyazo.com/4ae55fb11ce83e0aafd3240f1f3a7b2b.png" height="80%" width="80%" alt="tcpdump"/>

Create a custom rule to detect any original file name change for mimikatz on Wazuh
<img src="https://i.gyazo.com/c78656e40792f2b6ea84b5c51a15764e.png" height="80%" width="80%" alt="tcpdump"/>

Rename mimikatz.exe file to "youareawesome" and check Wazuh dashboard to see if any alert has successfully triggered.
<img src="https://i.gyazo.com/c23269e99094178cc8be17a25dabef78.png" height="80%" width="80%" alt="tcpdump"/>

Create a shuffler.io account and connect our wazuh manager to shuffler via the custom HTTP input trigger webhook URL.
<img src="https://i.gyazo.com/a5cef66f2837c340d0ac2ae7f17aab21.png" height="80%" width="80%" alt="tcpdump"/>

Run the "yourawesome.exe" from your mimikatz folder and run a scan on Workflow. After that, change the return value for the hashes and parse out only the hash values using regex
<img src="https://i.gyazo.com/4826eae86d8cb37d0f40c61e71d2bc9a.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/d9c5eb51a3f66bfbfd3b89d913199b49.png" height="80%" width="80%" alt="tcpdump"/>

Connect virustotal to Shuffle via API.
Automate sending hash values over to virustotal to check the reputation scores.
<img src="https://i.gyazo.com/ce185a93cfd79c51d0a06bb323988dfd.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/a5bf92073153a568da28a52a05aafc74.png" height="80%" width="80%" alt="tcpdump"/>

Create accounts on theHive dashboard and connect the API to Shuffler.io
Modify cloud firewall to allow all IP's coming inbound into port 9000 to allow us to test our automation.

How workflow should be looking at this point:
<img src="https://i.gyazo.com/85b2520173b5282ed374046606aaf613.png" height="80%" width="80%" alt="tcpdump"/>

Re-Run the workflow on Shuffler.io to see if the alert was created on theHive
<img src="https://i.gyazo.com/1de707a0fbae094b524cdc4f5ff82591.png" height="80%" width="80%" alt="tcpdump"/>

Add the email app and connect it to your workflow so alerts can be sent to your email as well:
<img src="https://i.gyazo.com/58b32a922d571635a3b5636ee471c5ab.png" height="80%" width="80%" alt="tcpdump"/>
<img src="https://i.gyazo.com/e3238b13ba32d94dec796a8eb348ea38.png" height="80%" width="80%" alt="tcpdump"/>


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
