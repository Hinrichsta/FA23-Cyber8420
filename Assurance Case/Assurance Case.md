# Assurance Cases

## Claim 1: Nextcloud minimizes malicious input execution
#### Description
User input is processed by nexcloud for searches, login, comments etc. This input can very well be used to perform many malicious activites such as extracting information from the database or executing complex script on the user's machine or even on the server. User's input represent a critical data that must be handled with care otherwise it could have some serious repercution for the business. 
The Assurance Case below seek to mitigate this risk. 

![Malicious input Execution](./Assurance%20Case%20-%20Malicious%20Input.png "Malicious Input Execution")


## Claim 2: NextCloud eliminates unauthorized account access
#### Description
NextCloud uses an enhanced password policy and preferences inside of it to maintain secure access to accounts. Multi-factor Authentication (MFA) is resolved by the Claim 4 - Sub-Claim 4. This Claim identifies and works to show that unauthorized account access through means of password attacks is eliminated and the various mechanisms that are used to mitigate them. Through the explanations of the Evidence found below it is clear that the NextCloud Assurance Case for eliminating unauthorized account access is indeed possible and critical to avoid any compliance or user privacy violations.  

![Assurance Case - Account Access drawio](https://github.com/Hinrichsta/FA23-Cyber8420/assets/143133739/bb1240ba-577a-46e6-9bf6-1261e0efc286)

* Alignment: The claim that NextCloud has measures in place to prevent unauthorized access to accounts is aligned with the User Password Policy found here: https://docs.nextcloud.com/server/latest/admin_manual/configuration_user/user_password_policy.html. Several claims are used to support this and resolve any rebuttal of such claims.
  
* E1: Evidence 1 indicates that the auditing of password attempts and logins will be able to indicate lockouts due to brute force attacks. These audit logs can trigger alerts if necessary, but in most cases are ignored unless persisting through several lockout periods. When an account is locked out due to failed login attempts, the account will be automatically unlocked after a period of time. Should the password lockout be activated 3 consecutive times the SIEM would trigger alerts for more investigation into a potential ongoing attack.

* E2: Evidence 2 suggests that a dictionary attack can be mitigated by implementation of complexity rules in the policy that will not allow for dictionary passwords to be setup. Maintaining this setting is essential for overall security and preventing simple passwords.
  
* E3: Evidence 3 shows that a security auditing report can prove that credential stuffing will not be effective because passwords cannot be reused and passwords are checked against a known leaked password verification utility. These known password verification utilities are updated regularly and used by various password managers such as Google, LastPass, and more.

* UM1: Undermining these subclaims and evidence could be if a change is made to the system during an upgrade or unintended side effect of an upgrade. This is set to me resolved and prevented by the Change Management processes of the organization’s IT Department.

* E4: Evidence 4 will prove that as a result of change management and verification of settings post changes that these implemented claims and sub-claims will remain in effect and not be undone by any type of change or update. 


## Claim 3: Nextcloud provides acceptable communication protection for end users
#### Description
Nextcloud has the ability to be set up with secure communication protocols within it platform.  It also only communicates over Web Protocols making it easier to properly configure the secure protocols, which can all be found here [Nextcloud HTTPS Configuration](https://docs.nextcloud.com/server/latest/admin_manual/installation/harden_server.html#use-https).  With strong security configuration the vast majority of attacks can be blocked, and Nextcloud has offerings to help with all of these.  The big points within this is that TLS 1.3 is readily available and that you can enable HTTPS Strict Trasport Security which requires HTTPS to be used at all times.  With HSTS and strong Encryption Ciphers set up almost every attack reguarding communication can be mitigated.  
Unfortunately it doesn't do the best to document the interserver communcation protocals, and the federated files shares.  It also doesn't have a section of its public documentation that lays out proper firewall configuration with the ports that are required for the server to run.  With what it has the end user communication can be configured to be as secure as possible without including third party applications such as a Web Application Firewall.
### Diagram:
![Secure Communications](./Assurance%20Case%20-%20Secure%20Communication.webp)


## Claim 4: NextCloud provides secure mobile device connections
#### Description
NextCloud provides a highly secure Andriod application for moible device connections to it's servers. The program allows for secure and detailed user password requirements as shown here [NextCloud Password Requirements Setup](https://docs.nextcloud.com/server/20/Nextcloud_Server_Administration_Manual.pdf). When coupled with the administrative ability for an administrator to force password changes, disable user accounts and enforce MFA, NextCloud creates a highly secure enviorments for it's users. NextCloud also allows for a highly secure form of MFA in terms of it's API tie in to the application during setup, with the U2F protocol, such as a YubiKey as seen here [NextCloud MFA Setup](https://docs.nextcloud.com/server/stable/Nextcloud_Server_Administration_Manual.pdf).  While U2F is a great choice when trying to secure a user account but also in blocking MFA fatigue attacks.  Hower the NextCloud admin guide does not do a very good job in explaining the setup and configuration of U2F within it's software. Another important aspect of protecting NextCloud users and it's plattform is turning on and utilizing the brute-force API as shown here [NextCloud brute-force Protection Setup](https://docs.nextcloud.com/server/latest/admin_manual/configuration_server/bruteforce_configuration.html).  The only draw back to this setting is the neccesity of the system administrator to understand the Linux server enviorment and be able to properly edit configuration files. 
### Diagram
![Secure Mobile Device Connection](./CEH%20Mobile%20Device%20Assurance%20Case%20Final.png)

## Team Reflection & Contributions
Our team worked very efficiently this week.  Each person studied and understood the prior week’s software assurance information and was able to contribute to the team in a meaningful and professional manner. Everyone brought good ideas, thoughts and helpful criticism on each use-misuse case and how to start their diagrams prior to meeting with Dr. Gandhi.  After our meeting with Dr. Gandhi each person set to work and created what we feel to be true to topic diagrams for our final submission. Each diagram and description were completed on time and was looked over by at least one other student.  The team met twice during the week and once with Dr. Gandhi.  Each student did their own diagram, description, helped to update GitHub with the proper file uploads and markdown editing as needed. All in all, it was a solid week.


### [Project Page](https://github.com/users/Hinrichsta/projects/2/views/1)
