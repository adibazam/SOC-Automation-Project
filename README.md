# SOC-Automation-Project
<h2>Visual Representation of the SOC Automation Lab Workflow</h2>
<p align="center">
  <img src="https://i.gyazo.com/101d18e496e016840f069d9029aaa1fe.png" height="80%" width="80%" alt="SOC Automation Lab Workflow">
</p>

## Objective

The objective of this project is to start from scratch and create a fully integrated SOAR solution incorporating Wazuh & TheHive for case management. The SOC Automation Project aims to enhance cybersecurity operations by automating threat detection, incident response, and security monitoring processes.

## Tools Used

- **Windows VM**: Ensured coverage and monitoring in Windows environments.
- **Sysmon**: Provided detailed monitoring of system activity.
- **Wazuh**: Open-source security monitoring for event analysis and compliance management.
- **TheHive**: For case management and collaboration in incident response.
- **DigitalOcean**: Cloud infrastructure provider for hosting the environment.
- **Mimikatz**: Security tool used for testing and validating detection capabilities.
- **OSSEC**: Integrated for log analysis and intrusion detection.
- **Shuffle**: Automation tool for integrating workflows and triggering responses.
- **VirusTotal**: API integration for automated threat intelligence and reputation checks.

## Steps

1. **Installing and Implementing a Cloud Environment (Digital Ocean)**
2. **Configure a Firewall on a Cloud Environment**
    <p align="center">
      <img src="https://i.gyazo.com/7c2ed0d6f30cd93c356d0c13a3b615bc.png" height="80%" width="80%" alt="Firewall Configuration">
    </p>
3. **Implement Firewall Configurations for both Wazuh & TheHive Servers**
4. **SSH into Our Virtual Machine and Install Wazuh Including All Prerequisites**
    <p align="center">
      <img src="https://i.gyazo.com/fc455d8ae843a3129bfb03abe25bccff.png" height="80%" width="80%" alt="Install Wazuh">
    </p>
5. **SSH into Our Virtual Machine and Install TheHive Including All Prerequisites**
    <p align="center">
      <img src="https://i.gyazo.com/65f36e61e7749936d993d2bde0442e0f.png" height="80%" width="80%" alt="Install TheHive">
    </p>
6. **Configure All Files for Wazuh and TheHive via Virtual Machine.
 Once both Wazzuh and theHive have been configured on your server, they should both appear active and running on your host ip address:**
    <p align="center">
      <img src="https://i.gyazo.com/5f4f0a0941def2c95cc76e27cf79897b.png" height="80%" width="80%" alt="Wazuh and TheHive Running">
    </p>
8. **Add an Agent to Your Wazuh Manager**
    <p align="center">
      <img src="https://i.gyazo.com/52fe09d937f2cdb0a07ac7c9462e90ab.png" height="80%" width="80%" alt="Add Agent to Wazuh">
    </p>
9. **Install Mimikatz**
10. **Configure OSSEC Configurations to Ingest Sysmon Logs**
    <p align="center">
      <img src="https://i.gyazo.com/4ae55fb11ce83e0aafd3240f1f3a7b2b.png" height="80%" width="80%" alt="Wazuh Dashboard with Mimikatz Events">
    </p>
11. **Create a Custom Rule to Detect Any Original File Name Change for Mimikatz on Wazuh**
    <p align="center">
      <img src="https://i.gyazo.com/c78656e40792f2b6ea84b5c51a15764e.png" height="80%" width="80%" alt="Custom Rule for Mimikatz">
    </p>
12. **Rename Mimikatz.exe File to "youareawesome" and Check Wazuh Dashboard for Alerts**
    <p align="center">
      <img src="https://i.gyazo.com/c23269e99094178cc8be17a25dabef78.png" height="80%" width="80%" alt="Wazuh Alert for Mimikatz Rename">
    </p>
13. **Create a Shuffler.io Account and Connect Our Wazuh Manager to Shuffler via Custom HTTP Input Trigger Webhook URL**
    <p align="center">
      <img src="https://i.gyazo.com/a5cef66f2837c340d0ac2ae7f17aab21.png" height="80%" width="80%" alt="Shuffler.io Integration">
    </p>
14. **Run "youareawesome.exe" from Mimikatz Folder and Run a Scan on Workflow. Change Return Value for Hashes and Parse Out Only Hash Values Using Regex**
    <p align="center">
      <img src="https://i.gyazo.com/4826eae86d8cb37d0f40c61e71d2bc9a.png" height="80%" width="80%" alt="Workflow Scan 1">
      <img src="https://i.gyazo.com/d9c5eb51a3f66bfbfd3b89d913199b49.png" height="80%" width="80%" alt="Workflow Scan 2">
    </p>
15. **Connect VirusTotal to Shuffle via API**
16. **Automate Sending Hash Values to VirusTotal to Check Reputation Scores**
    <p align="center">
      <img src="https://i.gyazo.com/ce185a93cfd79c51d0a06bb323988dfd.png" height="80%" width="80%" alt="VirusTotal Integration">
      <img src="https://i.gyazo.com/a5bf92073153a568da28a52a05aafc74.png" height="80%" width="80%" alt="VirusTotal Scores">
    </p>
17. **Create Accounts on TheHive Dashboard and Connect the API to Shuffler.io**
18. **Modify Cloud Firewall to Allow All IPs Coming Inbound into Port 9000 for Testing Automation**
    <p align="center">
      <img src="https://i.gyazo.com/85b2520173b5282ed374046606aaf613.png" height="80%" width="80%" alt="Workflow Status">
    </p>
19. **Re-Run the Workflow on Shuffler.io to See if the Alert was Created on TheHive**
    <p align="center">
      <img src="https://i.gyazo.com/1de707a0fbae094b524cdc4f5ff82591.png" height="80%" width="80%" alt="TheHive Alert">
    </p>
20. **Add the Email App and Connect it to Your Workflow for Email Alerts**
    <p align="center">
        <img src="https://i.gyazo.com/4023d9af7a9c92b3a2e9bfb2185b9448.png" height="80%" width="80%" alt="Email Alerts">
            <img src="https://i.gyazo.com/e3238b13ba32d94dec796a8eb348ea38.png" height="80%" width="80%" alt="Email Alerts">
    </p>
