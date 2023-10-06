# Assurance Cases

## Claim 1: Nextcloud minimizes malicious input execution
#### Description
User input is processed by nexcloud for searches, login, comments etc. This input can very well be used to perform many malicious activites such as extracting information from the database or executing complex script on the user's machine or even on the server. User's input represent a critical data that must be handled with care otherwise it could have some serious repercution for the business. 
The Assurance Case below seek to mitigate this risk. 

![Malicious input Execution](./NC-Malicious_Input.jpg "Malicious Input Execution")


## Claim 2: NextCloud eliminates unauthorized account access

![Assurance Case - Account Access drawio](https://github.com/Hinrichsta/FA23-Cyber8420/assets/143133739/bb1240ba-577a-46e6-9bf6-1261e0efc286)

* Alignment: The claim that NextCloud has measures in place to prevent unauthorized access to accounts is aligned with the User Password Policy found here: https://docs.nextcloud.com/server/latest/admin_manual/configuration_user/user_password_policy.html. Several claims are used to support this and resolve any rebuttal of such claims.
  
* E1: Evidence 1 indicates that the auditing of password attempts and logins will be able to indicate lockouts due to brute force attacks. These audit logs can trigger alerts if necessary, but in most cases are ignored unless persisting through several lockout periods. When an account is locked out due to failed login attempts, the account will be automatically unlocked after a period of time. Should the password lockout be activated 3 consecutive times the SIEM would trigger alerts for more investigation into a potential ongoing attack.

* E2: Evidence 2 suggests that a dictionary attack can be mitigated by implementation of complexity rules in the policy that will not allow for dictionary passwords to be setup. Maintaining this setting is essential for overall security and preventing simple passwords.
  
* E3: Evidence 3 shows that a security auditing report can prove that credential stuffing will not be effective because passwords cannot be reused and passwords are checked against a known leaked password verification utility. These known password verification utilities are updated regularly and used by various password managers such as Google, LastPass, and more.

* UM1: Undermining these subclaims and evidence could be if a change is made to the system during an upgrade or unintended side effect of an upgrade. This is set to me resolved and prevented by the Change Management processes of the organization’s IT Department.

* E4: Evidence 4 will prove that as a result of change management and verification of settings post changes that these implemented claims and sub-claims will remain in effect and not be undone by any type of change or update. 


## Claim 3: Nextcloud provides acceptable communication protection for end users
#### Description
Nextcloud has the ability to be set up with secure communication protocols within it platform.  It also only communicates over Web Protocols making it easier to properly configure the secure protocols, which can all be found here [Nextcloud HTTPS Configuration](https://docs.nextcloud.com/server/latest/admin_manual/installation/harden_server.html#use-https).  Unfortunately it doesn't do the best to document the interserver communcation protocals, and the federated files shares.  It also doesn't have a section of its public documentation that lays out proper firewall configuration with the ports that are required for the server to run.  With what it has the end user communication can be configured to be as secure as possible without including third party applications such as a Web Application Firewall.
### Diagram:
![Secure Communications](./Assurance%20Case%20-%20Secure%20Communication.webp)


## Claim 4: 
- The Nextcloud ...

## Reflection

\## TODO: Write Reflection

 [Project Page](https://github.com/users/Hinrichsta/projects/2/views/1)