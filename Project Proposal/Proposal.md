## Contents  

[About GetFINHelp](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#about-getfinhelp)  
[Security Policies and Strategic Objectives](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#security-policies-and-strategic-objectives)  
[Secure Software Development Framework (SSDF)](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#secure-software-development-framework-ssdf)  
[Risk Management Framework](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#risk-management-framework)  
[Cryptography National Institute of Standards (NIST)](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#cryptography-national-institute-of-standards-nist)  
[Nextcloud Security Vulnerabilities Found](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#nextcloud-security-vulnerabilities-found)  
[Solution](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#solution)  
[Security related issues](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#security-related-issues)  
[Reflections](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#reflections)  
[References](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Project%20Proposal/Proposal.md#references)  
About GetFINHelp (GFH) Bank:	

GitFINHelp (GFH) Bank is a financial in institution, which have been in business for over twenty years. Its primary mission is to help and serve the community through challenging and difficult times. 
GitFINHelp (GFH) Bank collaborated with other businesses and organizations in reaching out to our large and small business owners. GetFINHelp recently was awarded a government grant to help better serve our community in providing competitive mortgage rates to our first-time homebuyers.
By reaching out to our community GetFINHelp to implement an advanced state of the art technology in computer systems across the nation. 
GFH advanced computer systems allow our mission partners to adhere to both state, federal and local policies in maintaining Payment Card Industry (PCI) Data Security Standard (DSS) compliance. 
GFH strategic governance ensure the industries best practices and standards in protecting consumer’s data in our business environment. Those strict standards which includes, state, local and federal regulatory compliance, security governance and implementing industries best practices is what GFH Bank a part from our financial competitors. 
Protecting the processing of customers data is the number one priority. When a credit card transaction is over the network, the goal is to ensure data transmitted is both secure and tamper proof against vulnerabilities or attacks.
“Our customers care deeply about security and so do we. Nextcloud aligns with industry standards such as Clause 14 of ISO/IEC27001-2013 and related standards.” (Nextcloud, 2023)
Security Policies and Strategic Objectives:  
GetFINHelp (GFH) Bank. Our business strategic plan compliments the three pillars of data integrity: Confidentiality, Integrity and Availability (CIA).GFH Bank focuses on the latest advanced technology in securing and maintaining our network from vulnerabilities and intrusions.  
For example, our software developers are certified and trained in software assurance. One of the key elements of software assurance development is to understand key fundamentals throughout the Software Development Lifecycle (SDLC).
Secure Software Development Framework (SSDF):
The Secure Software Development Framework (SSDF) version 1.1 instituted by the National Institute of Standards (NIST) SP 800-218 is a process which can be implemented for mitigating the risk of software vulnerabilities. 
This SSDF framework captures the process of people, processes and technology in performing a robust and secure process in software development. 
Risk Management Framework:
The Risk Management Framework uses a seven-step approach in defending internal processes in protecting our network:
Step 0: PrepareCreate a risk management strategy and assess the organizational risk tolerance
Step 1: Categorize SystemAccording to CNSSI 1253 Initiate the Security Plan
Step 2: Select Security ControlSelect your security controls based upon your network
Step 3: Implement Implement security architecture based upon security controls
Step 4: AssessAssess Security Controls
Step 5: AuthorizeSubmit Security Authorization Package (Security Plan, SAR and POA&M) to Authorizing Official who determines final risk assessment
Step 6: Continuous MonitoringContinuous monitoring of the network
Cryptography National Institute of Standards (NIST):
Cryptography is a technique used to mask data from being read or accessible through malicious actors. There are several solutions cryptography can be implemented to encrypt data. Refer to Cryptography | NIST for further guidance.
GetFinHelp (GFH) Bank implemented the following security control features in the Software Development Lifecycle (SDLC):
(AC)**Access Controls 
(AU)**Audit Controls 
CM**Configuration Management
I.	Software Usage Restrictions
II.	User-Installed Software
IA**Identification and Authentication
IR**Incident Response
Maintenance Tools
MP**Media Protection
PE***Physical and Environment Protection
PL**System Security Plan
PM**Information Security Program Plan
PS**Access Agreements
RA**Risk Assessment Policy and Procedures
PS**Access Agreements
RA**Risk Assessment Policy and Procedures
SA-8** Security Engineering Principles
SC-1 System and Communication Protection Policy and Procedures
•	SC-50 Software-Enforced Separation and Policy Enforcement
SI System and Information Integrity Policy and Procedures
•	SI-7 Software, Firmware, and Information Integrity
8.19 Installation of software on operational systems CM-5, CM-7(4)*, CM-7(5)*, CM-11*
Vulnerability History: 
Frank Karlistscheck, a former core contributor of the ownCloud application, founded Nextcloud in 2016. Frank left ownCloud, as he wanted to build a platform more focused on security and privacy. 
The vulnerability statistic of Nextcloud since 2016 shows a wide range of vulnerabilities from XSS, SQL Injection, Overflow etc.
Nextcloud Security Vulnerabilities Found:
The National Vulnerability Database (NVD) indicated a severity base code of 5.3. This severity code indicated there is a vulnerability weakness enumeration in the system. The vulnerability indicated an improper restriction of excessive authentication attempts. 
In resolving this issue, the following recommendations would be a viable solution:
•	Ensure the proper configurations settings of the system, such as the enterprise server are in place and configured properly.
•	Install the latest software patches to the latest version.  CVE-2023-39955 indicated the latest patch is 4.8.0
•	Recommend the proper security controls and mechanisms are in place based upon industry best practices and standards. 
Based upon previous months, Nextcloud Security Vulnerabilities (XSS) will need updating based upon the latest recommended patch. The latest patch release was on August 10, 2023. The last update was on August 16, 2023
CVE-2023-28999 File encryption: Known vulnerability on Nextcloud is an open-source productivity platform. If not mitigated, a malicious server administrator can gain full access to the encrypted folder. Published 03-30-2023. Last updated 04-07-2023.
CVE-2023-28647attacker can enable IOS files app and bypass Nextcloud pin/password protection. Recommend upgrading IOS app to 4.7.0. There are no known workarounds for this vulnerability.
CVE-287 Improper Authentication Authentication method does not prove the proper identity is correct. Published 07-19-2006. Last updated 06-29-2023.
Vulnerability Timeline:
 
Security Issues:
There was no security policy implemented or enforced for this open-source software
The open-source software does not align with industry best standards
There are no network diagrams documented 
There are no access controls, security controls or mechanisms in place to deny access to server 
There was no encryption in protecting consumers financial data. All data files must use encryption features when transporting files over an open or closed network. Perceived Threats 
Given the Nextcloud Files application there are numerous potential threats that could affect a user of the cloud-based sharing system.  Below is a list of potential threats and examples of those threats. 
·	Unauthorized Access -- Given the Nextcloud application is credential based there is always a risk from both internal and external brute force attacks along with common password guessing of the usernames and passwords. 
·	Stolen Data – Because our business is a bank the perceived value of our data is greater to thieves. Because of this the risk is higher for data breaches,
·	Phishing of creds – Because phishing campaigns are the common first step to intrusion of systems, would be attackers would leverage campaigns to gain system credentials.
·	Malware – Because we are using Nextcloud to host our file storage, malware is easily uploaded and downloaded through this service.  This malware could attack host machines, our Nextcloud servers or any other device on our network. 
·	DDoS – Because we have multiple bank locations the need for an external link to our Nextcloud services was established.  Because of this a DDos attack on those external connections could be leveraged.
·	Man in the Middle attack – If an attacker was able to gain access to a host machine, server or the bank network in general they could post up and create a connection between a host machine and the Nextcloud service allowing them to gain access to the data being pushed or pulled.
·	Loss of data – Bank data is very important for daily business.  Loss of data could be due to disgruntled employees, incorrect permissions given to employees or data stores in Nextcloud and hardware failure on both the host side and Nextcloud server side is always an issue.
Solution:
Recommendations the following industry best standards and guidelines for installing software code:
•	Installing the latest antivirus software
•	Recommend installing the latest version 4.8.0 patch
•	NIST Special Publication 800-218: Secure Software Development Framework (SSDF) Ver. 1.1
•	Recommend implementing CNSS1253 policy for all access controls, auditing and security controls
•	Follow Software Policy requirements when installing new software
•	Benchmark new software in a dev/test environment before installing a production environment
GFH Environment:
GetFINHelp (GFH) Bank uses Nextcloud Server to share secure documents with customers and clients. Customers and Clients can also upload securely to the system for File sharing to prevent PII (Personally Identifiable Information) from being physically or electronically mailed to the bank employees for processing. Nextcloud Server shares can be accessed by authorized employees of GFH Bank and clients can only access their files. Files to be shared can include Tax Forms, Bank Statements, Invoices, ACH Payment Receipts, etc. 
Nextcloud Files will have moderate interactions with Banking software to identify user accounts to file shares and ensure that user folders are only accessible from authorized parties within the GFH Bank employees or account holders. 
Files will be accessible by customers and clients from the Web Portal and Mobile App with the ability to download and upload. Based on links or access to files from Web and Mobile App some interaction will exist there for direct access to the appropriate shares. Security will need to be involved in at rest data as well as in transit for uploads and downloads. User authentication of Nextcloud Server will require Multi-Factor Authentication for access and will have periodic timeouts to ensure inactive sessions are closed. GFH Bank will follow guidance  based upon industry best practices such as password and security policies, encryption standards. 
GFH Bank is a financial instituted which is regulated and is in compliance with PCI and DSS standards according to federal, state and local laws. GFH Bank is a financial institution which is considered the gold standard in using best practices in maintaining data security. GFH Bank also follows the industry best practices with the Software Development Lifecycle (SDLC) framework to ensure processes are following in software assurance and development.
Licensing Agreement:
The Nextcloud application states the following as its license agreement.  “These Guidelines are published under Version 3 of the Creative Commons Attribution Share-Alike License, and are derived in part from the openSUSE Trademark Guidelines (April 20, 2015), which in turn is derived in part from the Open Solaris Trademark Policy 1.0 (May 5, 2008), the Ubuntu and Mozilla Trademark guidelines. We reserve the right to make changes to the guidelines at any time without notification. We last updated the guidelines on April 16 2020. “ 
For those who wish to contribute to the next cloud project they offer a multitude of ways.   
·	You can visit Nextcloud on GitHub at https://github.com/nextcloud. 
·	You can visit their forums at https://help.nextcloud.com/. 
However, Nextcloud present the following suggestions on contributing to their project for newcomers:
•	Create a test environment where you can run the software in Ubuntu or Debian, install tools such as Git, Docker, a webserver, PHP etc. 
•	Fork Nextcloud’s repo and create a copy of it for your own GitHub account. 
•	Clone the fork you just brought over to your own GitHub account. 
•	Create a new branch for each feature you would like to contribute. 
•	Make changes to the code. 
•	Test those changes to the code. 
•	Commit your changes to the code once tests are successful.  When committing make sure you are descriptive in your comments for yourself and others to understand better when you did. 
•	Push your changes from the branch to your GitHub repo. 
•	Create a pull request where your repo is the branch and Nextcloud is the main branch and compare. 
•	Fill out the pull request template.  Be very detailed in your request and follow Nextcloud’s guidelines or the template. 
•	Watch for any reviews and feedback given from the Nextcloud community. 
•	If your pull request is approved by Nextcloud they will merge it into the main Nextcloud repo. 
While Nextcloud doesn't have a "contributor agreement" form per say they do have a code of conduct policy. The code of conduct rules applies to the following guidelines: 
•	Contributors will use common sense
•	Be considerate, respectful and mindful of others’ ideas of the Nextcloud Community
•	Be supportive of others by embracing, asking for help and embracing the Nextcloud’s General Community 
Project Description:
The contributors consist of a growing number of highly reviewed individuals that number as of this document's writing, 890. As the community grows the support and contributions grow with it making it an ideal choice for open-source software. Activity for this open-source software has been steady since the software was first created as a repository and is updated through contributions and branches monthly. The community of followers is active and helpful for resolving potential issues. 
The Nextcloud software has many uses and continues to innovate in the sectors it operates in and has many repositories that cover a wide range of use cases. Popularity of Nextcloud is immense with nearly 4K subscribers and yearly conferences hosted in Germany to showcase new features and developments. HTML, CSS, JavaScript, PHP, and VUE.js are just some of the primary languages this software is written in. The application is designed to be run on Apache in the Linux OS. This web and mobile accessible application can be styled in many ways. The front-end settings and configuration are done in Vue.js and compiled with css written in SSCC. Future compatibility with containerization is being discussed in several issues. Documentation for this open-source project can be found in the GitHub repository and on its linked site 

Reflections:
Extremely difficult to find software which software developers continued to develop and maintain. I reviewed several files for this project and found I was going into the land of the abyss! From a cyber-security standpoint, I did not see any industry best practices when it came to securing software based on guidance such s NIST SP 800-53 rev 5. I recognized the software developers use this opens source code by making additional tweaks to install on their organizational network. I could not verify if the developers performed a benchmark test before implementation on the production environment. I would only hope before implementing any open source software, the software developers test the software on all three networks (development and test) before placing on a production environment. I would also suggest understanding and knowing the operational environment before installing any software. GItFINHelp (GFH) Bank primary focus is to follow guidelines and industry best standards in software assurance and development.
Team Motivation:
Our team decided to go forward utilizing a file sharing system as the base of our project.  File shares are a big part of an organization as it allows for easy collaboration and can be centrally managed.  This also adds aa certain level of risk such as target attacks. As malicious actor can penetrate a file share system and cause extreme damage into the organizational assets.
Initially, we were looking at a much smaller scale project. As we looked at other projects, we decided to work on Nextcloud. Nextcloud gave us an opportunity to start with a baseline and add other opportunities to apply necessary skills in software assurance.  
Nextcloud files was on a much larger scale and offered a lot of features just within the file system. Nextcloud would be perfect opportunity as we apply the baseline for the financial institution that we are working on.  The opportunity to build a  web GUI system on a central application server can be applied across various operating systems.  The Nextcloud files system was exactly what we were looking for in our project.

References: 
BAI – Risk Management Framework Training | Home Page. https://rmf.org/. Accessed 8 Sept. 2023. 
“Cryptography.” NIST, June 2016. www.nist.gov, https://www.nist.gov/cryptography.
Data at Rest Capability Package, version 4.0, January 2018 https://www.nsa.gov/portal/75/documents/resources/everone/csfc/capability-packages/dar-cp.pdf
Force, Joint Task. Security and Privacy Controls for Information Systems and Organizations. NIST Special Publication (SP) 800-53 Rev. 5, National Institute of Standards and Technology, 10 Dec. 2020. csrc.nist.gov, https://doi.org/10.6028/NIST.SP.800-53r5.
National Security Agency | Central Security Service. https://www.nsa.gov/. Accessed 8 Sept. 2023. “Nextcloud Code of Conduct.” Nextcloud, 7 Sept. 2023, nextcloud.com/contribute/code-of-conduct. 
Nextcloud : Security Vulnerabilities, CVEs Xss, Cross Site Scripting. https://www.cvedetails.com/vulnerability-list/vendor_id-15913/Nextcloud.html?page=1&opxss=1&order=1&trc=33&sha=30206647962e12ae4a525c212e9db9b3c055046b. Accessed 8 Sept. 2023.
“Nextcloud Community.” Nextcloud Community, https://help.nextcloud.com/. Accessed 10 Sept. 2023.
“Contribute.” Nextcloud, https://nextcloud.com/contribute/. Accessed 10 Sept. 2023.
“Nextcloud Trademark Guidelines.” Nextcloud, https://nextcloud.com/trademarks/. Accessed 10 Sept. 2023.
NVD - CVE-2023-39958. https://nvd.nist.gov/vuln/detail/CVE-2023-39958. Accessed 8 Sept. 2023.
NVD - CVE-2023-28647. https://nvd.nist.gov/vuln/detail/CVE-2023-28647. Accessed 8 Sept. 2023.
NVD - CVE-2023-28999. https://nvd.nist.gov/vuln/detail/CVE-2023-28999. Accessed 8 Sept. 2023. “Official PCI Security Standards Council Site.” PCI Security Standards Council, https://www.pcisecuritystandards.org/. Accessed 8 Sept. 2023.
