# Automated SOC Components Setup Script

## Overview


<img width="433" height="310" alt="Image" src="https://github.com/user-attachments/assets/f7b3cd3b-03b8-4792-8a7c-38ce13450832" />

This script automates the setup of a comprehensive security monitoring environment, including a Security Information and Event Management (SIEM) system,Network-based Intrusion Detection System (NIDS) and Host-based Intrusion Detection System (HIDS) on a single machine. It streamlines the installation process, making it accessible to users with different levels of technical expertise.

**Note:** This script is intended to install all the components on a single machine, meaning the same box will have the SIEM, NIDS, and HIDS core components.

## Components

The script facilitates the installation of the following SOC components:

1. **SIEM (Security Information and Event Management):** This component combines Elasticsearch, Kibana, and Filebeat to provide a powerful platform for monitoring and analyzing security events in your environment. The SIEM setup includes Elasticsearch, Kibana and Filebeat version 7.17.13 as it is the compatible version to integrate with Wazuh manager version 4.5
   ![Image](https://github.com/user-attachments/assets/8b948e16-b4db-43ff-9401-00390eeb3977)


2. **NIDS (Network-based Intrusion Detection System):** Suricata, a high-performance NIDS, is configured to help protect your network from intrusions and suspicious activities.
**Note:** Suricata will monitor the local interface of the machine where it is installed. To monitor the entire network traffic, it should receive traffic from a TAP device or a SPAN port.


3. **HIDS (Host-based Intrusion Detection System):** The script installs the Wazuh Manager, an open-source HIDS. It aids in monitoring, detecting, and responding to security threats on individual hosts. The setup includes the installation of Wazuh Manager version 4.5

   ![Image](https://github.com/user-attachments/assets/5d145513-5545-47eb-b7e7-e7c69616e803)

   ![Image](https://github.com/user-attachments/assets/1d64c49d-4093-47b5-bb69-5c2a9b2596ef)

   ![Image](https://github.com/user-attachments/assets/12a6605f-8c8c-4e44-9aa2-262466541132)
   

## System Requirements

Before running the script, please ensure that your system meets the following requirements:

- Ubuntu OS
- Minimum 4GB of RAM
- Minimum 20GB of free disk space

If your system doesn't meet these requirements, the script will issue a warning and allow you to proceed at your own risk.

## Usage

1. Clone this repository to your local machine:

   ```bash
   sudo apt update

2. Clone this repository to your local machine:

   ```bash
   sudo apt upgrade -y

3. Clone this repository to your local machine:

   ```bash
   sudo apt install git curl net-tools vim lolcat figlet

4. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/Zahin-Azmaeen/soc_setup.git

5. Navigate to the repository's directory:
   ```bash
   cd soc_setup

6. Make the setup_script.sh executable:
   ```bash
   chmod +x setup_script.sh
   
7. Execute the setup_script.sh:
   ```bash
   sudo ./setup_script.sh
   
8. Follow the on-screen prompts to choose which components you want to install and continue with the setup.
   Post-Installation Steps
9. After successfully running the script and completing the NIDS (Suricata) setup, consider the following post-installation steps:

## Verify NIDS Logs: 
Check if logs are getting written to the /var/log/suricata/eve.json file. This is essential for monitoring network traffic.
Besides, you need to check from kibana if data is being displayed in Suricata Dashboard.

## Wazuh-Agent Installation: 
To complete the setup and ensure effective security monitoring, install Wazuh agents on Linux or Windows machines in your network. This allows you to ingest logs into the SIEM, enhancing your security monitoring capabilities.

## Warnings and Considerations
Data Backup: Before proceeding, it's advisable to backup your data, especially if you plan to run the script on a production system.

## Security Best Practices
After setting up the security components, consider following best practices for system hardening, firewall configurations, and securing sensitive data.






   

