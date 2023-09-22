##Part 1 - Misuse Case Diagrams

### Misuse Case example 1 - File Access
![File Access](./Use-Misuse%20Case%20-%20Access_Files%20-%20Version1.png "File Access")

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