# Cowrie Honeypot project
Cowrie is a powerful platform for establishing a honeypot. The honeypot can be used to attract attackers and bots and record all of their movement within the virtual environment as they traverse the honeypot. Most notably, they honeypot will capture and download any payloads that are ran in the environment. This creates the opportunity for malware analysis of the payloads in a secure environment.


## Install Cowrie
Cowrie can be installed by following. 
https://cowrie.readthedocs.io/en/latest/INSTALL.html

## Cowrie Honeypot Configuration
My cowrie honeypot runs openly on the internet via a virtual machine in the cloud. This approach will eliminate the need to expose my personal network to attacker and safely monitor and study the tactics of threat actors. The VM runs with the following specifications:

- OS - Ubuntu x64
- vCPU/s: 1 vCPU
- Storage: 25 GB NVMe

Cowrie running on my cloud VM (bin/cowrie status)
![image](https://github.com/user-attachments/assets/f3127104-a3c6-48f1-93cc-7318a6320cfa)

## Cowrie Logs
Honeypot activity is logged into daily folders which are used to review the activities as they happen on the honeypot. These logs can be useful for correlating events based on time when forwarded to a SIEM tool. 

Log captures of attacker activity(logs at: /cowrie/var/log/cowrie)

<img width="807" alt="cowrie_log_capture" src="https://github.com/user-attachments/assets/3952a294-2d5e-4ac2-883e-a359f183d724">

![image](https://github.com/user-attachments/assets/4ae81669-19b3-4d47-ba58-532860ae59e9)

## Cowrie Honeypot Recorded Sessions
Cowrie will record each ssh/telnet session that is opened by attackers. These sessions can be played back to perform a live analysis of the exact actions performed by the threat actor and can reveal useful information such as commands ran by the attacker and any IP addresses used to download malware onto the honeypot server


Recorded sessions availiable for playback on my honeypot (/cowrie/var/lib/cowrie/tty):

![image](https://github.com/user-attachments/assets/05b62891-c29b-4243-9de5-8657cb8f594b)

Playback - threat actor commands captured and displayed for playback using playlog command

![image](https://github.com/user-attachments/assets/15bdac61-296b-4a72-917d-0c88786a6f85)

## Cowrie Honeypot Downloads(/home/cowrie/var/lib/cowrie/downloads)
Our downloads folder contain any files that are downloaded to the honeypot server. These downloads can be further analyzed using a text editor or decompiled and quarantined into a malware analysis lab to study the behavior of the malware when detonated.

Cowrie downloads folder displaying all the downloaded files from threat actors:

![image](https://github.com/user-attachments/assets/0defc7fe-1e3a-45bc-aaf3-beb69358a070)

View payload downloaded to server by threat actor:

<img width="657" alt="cowrie_download_review" src="https://github.com/user-attachments/assets/d340f74a-5074-49a8-946e-a663428755b3">


