# 🟢 Greenbone-OpenVAS-Installation-on-Kali-Linux 🦴

This showcases the installation process for the Security Vulnerability Scanner Greenbone/OpenVAS on a Kali Linux OS based from June 2023. 
The Vulnerability Scanner will be used to assess my mock enterprise network lab from a Cybersecurity Defender perspective, as well as Cyber Threat Actor looking to find more vulnerabilities on a network they gain access on. 

To see the mock enterprise lab this will be ran on, see my page: [ESXi-Home-SOC-Lab-Network-Overview](https://github.com/gervguerrero/ESXi-Home-SOC-Lab-Network-Overview)

I used a helpful guide to help with the installation process:
https://www.ceos3c.com/security/install-openvas-kali-linux/?expand_article=1

The following command was used to update and upgrade the Kali repository and had a -y option to bypass yes or no confirmation prompts with yes. (APT = Advanced Package Tool)

![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/caa7a0f3-d9a5-41db-a31c-cf62e453342d)

![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/30dee7b4-8a81-4314-b575-b4842d240b7e)

<br/> 
<br/> 

The next command actually installs the Greenbone/OpenVAS files onto the system:

![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/8ff06680-d7bc-4ec8-9740-aa1f43a2adb1)
![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/23c53c81-e8cb-48c9-947c-a69263540904)

<br/> 
<br/> 

The next command actually initiates the configuration and deployment of Greenbone/OpenVAS:

![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/8eb4f343-dfe2-4508-89aa-b419d8febe95)
![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/7cef1c2d-347c-4b2e-8eb1-26ccef735d2a)

<br/> 
<br/> 

Reading the bottom of the last picture, we can see it tells us to run the command: "_gvm-check-setup_" to verify the configuration was configured properly:

![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/cd75b1cf-75c4-4b87-8872-9ac19545b009)
![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/8e58fd88-cb0d-4439-b808-774d535dbe7f)

^^^ Seen above in the photo, there is an Error where the Postgresql DB does not exist.

It's at this point I've tried to run the command shown on the screen to try to fix the issue:

"_sudo runuser -u postgres -- /usr/share/gvm/create/create-postgresql-database_"

It didn't resolve the issue, so I turned to online forums to find that others were having the same problem:

https://forum.greenbone.net/t/the-postgresql-db-does-not-exist/15239

One of the comments on the forum suggested to try installing Greenbone/OpenVAS without using the update commands as it might be causing some collision issues or duplicate files that hinder the installation/deployment process:

"_sudo apt update && sudo apt upgrade -y_"

![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/2df4e08d-0926-4061-884c-c336412e7579)


From here I reverted my Kali Linux virtual machine to a snapshot prior to installing anything. I downloaded and ran the configuration/deployment for Greenbone/OpenVAS. Upon finishing, I noticed this time the admin user and password was displayed this time:

![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/4f26411a-cbbf-453f-8374-1b48ef70fa9d)

Following the "_gvm-check-setup_" command, the installation appeared to be ok, which was different than the first time that returned errors:

![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/92802778-3af5-45bc-8721-30f291645b21)

I was able to successfully return the Greenbone/OpenVAS page on a web browser with "_https://127.0.0.1:9392_" (9392 is the default port in use for Greenbone/OpenVAS services.) 

 ![image](https://github.com/gervguerrero/Greenbone-OpenVAS-Installation-on-Kali-Linux/assets/140366635/49e415b9-84c4-4256-aa8e-8fe0ff7415ec)
