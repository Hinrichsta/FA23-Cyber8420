##Part 1 - Misuse Case Diagrams

### Misuse Case example 1 - File Access
![File Access](./Use-Misuse%20Case%20-%20Access_Files%20-%20Version2.png "File Access")
#### Use Case  
Bank employees, customers, and even the partners that will be sending or receiving files from GFH Bank will all be targets of the hacker groups specifically Legion of Doom who will be attempting to gain access to files through login hacking attacks. When the employees, customers, and partners access files they will need to go through a login portal and use credentials to access this portal. Other measures not outlined in this use case such as MFA and one-time time based-passwords (TOTP) will be implemented alongside a strongly configured User Password Policy.

#### Misues Case  
The hacker group Legion of Doom is a threat to our Customer and Banker files that include PII (Personally Identifiable Information). With access to files compromised, they would be able to steal identities, create fake accounts, and much more with customer data. The misuse could incorporate many different forms of attacks such as Brute Force Attacks, Dictionary Attacks, and Credential Stuffing. These attacks have various forms of prevention built into the NextCloud Server User Password Policy and thus it should be fully implemented with all its feature capabilities to prevent these issues.

### Prevention of misuse case
To prevent the misuse of the access to files, NextCloud Server has a strong and multi-optioned Password Policy that can be found here. 
https://docs.nextcloud.com/server/latest/admin_manual/configuration_user/user_password_policy.html
A password policy is a set of rules designed to enhance computer security by encouraging users to employ strong passwords and use them properly.

In the security-section of your administrator-settings you can configure:
* A minimal length of a password. Default is 10 characters.
* A password history
* A password expiration period
* A lockout policy
* To forbid common passwords like ‘password’ or ‘login’.
* To enforce upper and lower case characters
* To enforce numeric characters
* To enforce special characters like ! or :
* To check the password against the list of breached passwords from haveibeenpwnd.com (hashed check via haveibeenpwnd.com-API)
![image](https://github.com/Hinrichsta/FA23-Cyber8420/assets/143133739/c7aed762-ae92-47bb-9618-102228f44977)

* Brute Force Attack
  * Will be prevented by Password Policy - Account Lockout Enabled after 5 invalid attempts.
* Dictionary Attack
  * Will be prevented by Password Policy - Forbid common passwords like ‘password’ or ‘login’ and  checking the password against the list of breached passwords from haveibeenpwnd.com
* Credential Stuffing
  * Will be prevented by Password Policy - A password history and checking the password against the list of breached passwords from haveibeenpwnd.com.
    
### Misuse Case example 2 - Website Access
![Website Misuse Case](./Website%20Misuse%20Case.webp "Website Misuse Case")

#### Use Case  
Bank employees are allowed to use the website of Nextcloud in order to access their files from computers at home.  This is used for all versions of the file system desktop app, mobile app, and the webpage.  This is useful for employees who will work from home and employees that may need to travel to different locations for various reasons.  Users will navigate to the subdomain URL in a browser or configure the applications to point to it.  They will then have to use their credentials and other provided security measures, such as MFA, to authenticate and access their files.

#### Misues Case  
Data thieves will try their hardest to get ahold of our banks data and use it to extort money from us or to sell to the highest bidder for other purposes.  They will employ various methods that are well known attacks for internet facing applications, with the chief most being attempting to manipulate our users into giving up the information without even knowing they are doing it.  Employing these mathods can take time and resources, but they are well funded from their thefts over the years and they have the resources to stand up attacks quite quickly.  They will employ any means necessary to gather our data so that they can hurt us and make some easy money

### Prevention of misuse case
* Packet Sniffing
  * This is easily preventable by using TLS Encryption.  By Encrypting our data the Data Thieves cannot easily access what is being transferred between our server and the client.
* TLS Stripping
  * This can be prevented by automatically redirecting all connection to utilize the secure site, and blocking all connection requests to the unsecured site
* TLS Downgrade
  * This can be prevented by requiring the use of the latest version of TLS at every aspect of interaction.  If a user isn't connected via TLS 1.3 then access is rejected.
* TLS Exhaustion
  * These attacks are effectively a DDoS, and are difficult to prevent.  The best way to do this would be to make the site internal only, and require a VPN to access the site.


### Misuse Case example 3 - Database
![Database Misuse Case](./Use-Misuse%20Case%20-%20Database.png "Database Misuse Case")

### Misuse Case example 4 - Mobile App

### Misuse Case example 5 - System Administration


## Part 2 - OSS Project Documentation  

## Reflection
