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
#### Use Case
A banker seek to pull client's account information or search through the company home page information related to client inquiry. To do so they interact with search boxes which behind the scene query the bank database. 

#### Misuses case
The darkweb is filled with various skilled programmers and hackers who can't wait to put their hand on your precious client record. They will try everything in their power to gain control of those record including attacks like XSS or SQL Injection which essentially seek to exploit weak entry data point (User's input) in the bank application or website that have not been properly sanitize. Where a regular banker would enter a normal query, the darkweb data harvester would enter malicious codes. 

### Prevention of misuse case
* Client side input validation: To counter XSS and SQL Injection, the nextcloud system should sanitize all users input not only on the client side but most importantly on the server side. Client side controls can easily be disabled or bypassed by a malicious actor like the darknet data harvesters. 
* Server side input validation: Everything happening on the client side can be controled by the client however server side implementation is not. 
* Use parametized sql queries: Even when the data is sanitized on the server side SQL Injection can still be possible as some advanced attack like blind SQL Injection can be hard to defend against. This is why in addition to server side validation nexcloud should use parametized query. 
Parameterized queries is a technique that aims to separate the SQL query from the user input values. The user input values are passed as parameters. They can no longer contain an executable code since the parameter is treated as a literal value and checked for the type and length.

### Misuse Case example 4 - Mobile App
![image](./CEH%20Mobile%20Device%20Use-Misuse%20Case%20Draft3.png)
#### Use Case  
From the banker’s point of view who would use their android smart phone to access their NextCloud application, would login with their username and password and then authenticate with U2F over NFC. They preferably would use a password vault, so their password is complex. 

#### Misues Case  
From the WFFHG(Wells Fargo Funded Hacker Group)’s perspective, they would have already phished, purchased off the dark web or otherwise, the bankers NextCloud credentials for login.  They may also have planted malware on the device that would allow them to intercept MFA tokens via text messages or phone calls.  They could also leverage MFA fatigue attacks to hopefully wear down the banker into accepting the incoming MFA authentication request.

### Prevention of misuse case
With regards to Nextcloud’s ability to counter the WFFHG attacks the administrator of the NextCloud system could leverage a force password change if the credentials were known to be leaked.  They could also disable the user account in total. However, the best defense to nullify any MFA attack would be to use a U2F (YubiKey or equivalent) for only-on-person authentication to NextCloud MFA prompts over Android using an NFC connection.

In NextCloud's admin Manual online, in the two-factor authentication chapter it covers the following:
* Two-factor authentication is installed by default, this allows for TOTP and U2F.
* In order to use two-factor authentication the administrator must enable which form of two-factor they want used. In this case U2F.
* Next the admin must enforce the U2f authentication for all employees and groups.
* When users logon to the NextCloud application they will be prompted for setting up U2F with a YubiKey.
![image](./U2F.png)

* MFA fatigue attack
  * Will be prevented by a Admin disabling a user account.
  * Utilizing U2F MFA with a Yubikey.
### Misuse Case example 5 - Customer
![Misuse Case 5](./GFH%20Bank%20Misuse%20Case%20Diagram%20Customer.png)
Scenario: The customer is reviewing her account balance on the internet. In the background, GFH Bank is allowing here access by validating asymmetrically (utilizing both public key and private key). She is logging onto the bank’s HTTPS website. In the meantime, vulcanator is trying to infiltrate the system by denying the customer access to her account. Vulcanator introduced a botnet on the bank’s server while performing a distributed denial of service attack on the banks website.  
While the DDOS is in place, vulcanator is also capturing trying to capture the customers data such as user name, password, bank login credentials, etc. by running a script kiddie to capture this information.  
GFH Bank have in place a public key (for the customer) and private key (for the bank) to authenticate information being sent and received to validate the customers credentials.
In the meantime, the incident response team have detected anomalies in the event logs which triggered an alarm on the system. 
Vulcanator credentials were invalid, as indicated in the event logs. GFH also have in  place packet sniffers who detected an invalid ip address on the network.  


## Part 2 - OSS Project Documentation 
Nextcloud has an extensive database of documentation, and most of it is available for free on their website at https://docs.nextcloud.com/.  Their documentation covers just about anything that you could wish for from your basic maintenance and installation of the server to Adding artificial intelligence.  Nextcloud is also a quite large project and no project is immune to vulnerabilities, Nextcloud makes it very prominent that security is a focus for them.  

### Security configuration
While the security configuration of Nextcloud appears to be well documented, they do have their share of vulnerabilities.  They don’t try to hid their vulnerabilities posting their [CVE Details page]( https://www.cvedetails.com/vulnerability-list/vendor_id-15913/Nextcloud.html) they have had 272 vulnerabilities over their lifetime with 62 within 2023.  They also have a direct link to submit reports to [HackerOne]( https://hackerone.com/nextcloud) about their vulnerabilities.  It seems that most vulnerabilities found are submitted through the HackerOne page and that they patch them efficiently.  
* [Basic Server Hardening](https://docs.nextcloud.com/server/latest/admin_manual/installation/harden_server.html)
  	* [Using HTTPS](https://docs.nextcloud.com/server/latest/admin_manual/installation/harden_server.html#use-https)
* [User Management]( https://docs.nextcloud.com/server/latest/admin_manual/configuration_user/index.html)
  * [User Password Policy]( https://docs.nextcloud.com/server/latest/admin_manual/configuration_user/reset_admin_password.html)
  * [Multifactor Authentication](https://docs.nextcloud.com/server/latest/admin_manual/configuration_user/two_factor-auth.html)
  * [Brute Force Protection]( https://docs.nextcloud.com/server/latest/admin_manual/configuration_server/bruteforce_configuration.html)
* [Server Side Encryption]( https://docs.nextcloud.com/server/latest/admin_manual/configuration_files/encryption_configuration.html)
* [Transactional File Locking]( https://docs.nextcloud.com/server/latest/admin_manual/configuration_files/files_locking_transactional.html)

### Installation
The installation of Nextcloud is also quite well documented within their [installation documentation page](https://docs.nextcloud.com/server/latest/admin_manual/installation/index.html).  The installation of the server application is done on linux and can be done manually or through a couple of different automatic configurations such as Snap.  They also provide their [deployment]( https://portal.nextcloud.com/categories/Scalability/Deployment-recommendations) and [database recommendations].  Overall they do make it quite easy to install the server for the application, especially with such a large project.  

### Issues
There are a lot of potential pitfalls with their method of documentation, as it is easy to get lost in.  While going through the Security and Installation documentation I regularly got lost attempting to find information on database configuration as I thought it would be in one section, but it was in another.   They also hide their deployment recommendations behind a login page. While it doesn’t appear to cost anything to create a login and get this information, it does make it more difficult for the casual user or researcher to get their information.  There appears to be quite a bit of information hidden behind the login and it is possible that some items were missed due to this login requirement.  


## Reflection
* Lucas Reichlinger
  * For contributions this week I hosted the meetings, worked through Use Case Example 1 for Login to the Files, and helped members work with Draw.io the diagram tool used for the assignment. Worked with each member to help gain a better understanding of the requirements set forth by the instructor based on a previous meeting and resolved any previous diagrams for assignments to ensure project documentation was accurate. Proofed writings for part 2 of the assignment to ensure accuracy and grammar. Some of the issues that occurred were related to time management, workload, and use of the tools for the project. We resolved them by working toward a common goal, helping each other where possible by staying late at meetings to ensure all questions were answered, and dividing tasks among group members based on skill sets. Each member also contributed to the improvement of each other's diagrams to help maintain a full understanding of the assignment. Going forward it was recommended that our meetings be more organized in terms of agenda and getting through any misunderstandings, as well as working earlier on the project when it is posted when time permits for everyone.
 
* Chris Hepburn
  *	Section 2 reflection - Prior to our first meeting this week I created a working area in our Microsoft Teams group (Files)along with color coded Todo document to get ideas going. For the first meeting we all discussed our understanding of the material and what use/misuse ideas everyone had along with company ideas. The next day we met with Dr. Gandhi where we discussed our use/misuse ideas where he gave us food for thought in being more to the point and having a company that would be larger and broader. After this meeting Sheryl and I met on Zoom for more dialog and questions using draw.io.  I completed my use and misuse case on mobile device MFA login using U2F (YubiKey) with NextCloud to combat MFA fatigue attacks specifically. I typed up my use case and misuse case summaries of the diagram and team contribution summary along with team reflection.  After this I fleshed out my use/misuse task in github with my dialog with Dr.Gandhi and uploaded my draw.io drafts, needed pictures for the summary and all written items.  
  *	Team reflection- This week our team met two times for an hour or more and one time with Dr. Gandhi.  Sheryl and I moved to a different zoom meeting after meeting with Dr. Gandhi to help clarify the project to that point for about 30 minutes.  The team does have more alpha types than not which makes for many leaders.  However, we all have the common goal, which is to get the assignments done, to make sure others understand the tasks at hand and how to complete them. While the team may have different views on some tasks, we talk it out and ultimately come to an agreement and help one another when there are questions, misunderstandings, ideas on making assignments flow better or needed communication within the group. I did feel the diagrams were rather difficult to achieve the initial idea fully of what was wanted from Dr. Gandhi, but we all pulled together and fleshed it out and made sure each person understood what was expected in the end.  

* Henri Allou
  * Individual Contribution:
    My contribution this week has been to work with my teammates to complete the deliverable for the Requirement for Software Security Engineering. On Tuesday we met and discus what nextcloud features we would like to develop use/misuse cases for and assigned them to each team member. I picked the database as it talk more to me than the other features. We had 1 day to get a draft of the diagram ready for Dr Ghandi to review on Wednesday. This was a rather short timeframe I think from when we picked our task but we managed to have 3 drafts ready. Dr Ghandi guided reviewed the draft and put us on the right path by adjusting our understanding of what was needed. We decided to meet again on Thursday from 5pm to 5:30pm to help each other out and review our diagram on Thursday. Some members had difficulties with the use of Github or draw.io. Many stayed well past 5:30pm to help each other out. I stayed until 7pm with Sheryl to help her with her diagram on draw.io (an extra hour and half past 5:30pm) 
  * Teamwork Reflection:
   As a team we communicate a lot through emails on canvas. I find this team to be very communicative, which is great for any project as communication I think is key to a successful project. We discuss openly about any issues we have working on our tasks and help each other out. Some go as far as proposing extra meetings with members who need help. This is very refreshing to see. It means we are all on the same page and willing to put in all the effort we can to get to the finish line. I hope this great teamwork will continue until the end. 

* Tyler Hinrichs
   * In this project I worked on the Website misuse case and did most of the project board organization.  Initially I started with an API misuse case, but it ballooned a lot and so I narrowed it down to just the website and specifically looked at SSL within the Website.  It took a while to finally get what I needed, but after the review with Dr. Gandhi I had a decent grasp on what was expected.  After reviewing past projects I felt I had a solid grasp.  The project board was mainly just assigning the tasks and keeping an eye on everything, which was monitored through email.  I had to do a little pushing for everyone to use it but overall it had moderate use.  
   * The group could use a little more work in terms of working cohesively, and I do not think that we will make it to the finish line of this semester as we currently stand.  This past week and a half has been a trial of my patience and my friends and coworkers will to hear me vent.  I believe that if we have a meeting shortly after the assignment is posted it may help our group work better, but I don’t think it will help fix the root cause of our issues.

* Sheryl Cummings
   * [Reflection](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Software%20Security%20Engineering/OSS%20Nextcloud%20Security%20and%20authentication%20featuresv3.docx)
