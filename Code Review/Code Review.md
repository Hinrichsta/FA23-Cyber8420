# Code Review

## Introduction

Our team decided to take a scenario-based approach.  We felt this would be wise as we had one team member who focused primarily on the NextCloud mobile app which was it's own repo within GitHub.  In researching the MITRE website for inline CWE’s 400 and 547 seemed feasible and potentially obtainable by an attacker. The other three team members focused on the larger overarching NextCloud server application repo on GitHub.  This is tied in to file access, website access and database access, all within our original misuse case. They focused on the CWE’s 200, 836, 295, 918???

## Code Review Strategy  
We decided to utilize 2 different automated code review tools for reviewing each of our CWEs so that we could cross reference and make sure potential issues were caught.  Manual reviews were then used to verify that the CWEs were not present within the application.  For the both the Server and the Mobile app they were reviewed with CodeQOL which is built into GitHub.  For the server it was secondarily reviews by Sonar Graph which is good for web applications, and the Mobile app was reviewed by Snyk and SpotBug which were better for Java applications.  Once the tools were run the found Weaknesses were reviewed to check against the ones we were looking for, failing that the manual review would be performed.

## Reviewed CWEs

* CWE-400  (Chris)
* CWE-547  (Chris)
* CWE-611  (Henri)
* CWE-200  (Henri)
* CWE-79   (Henri)
* CWE-1022 (Luke)
* CWE-836  (Luke)
* CWE-295  (Tyler)
* CWE-918  (Tyler)

## Chris  
### CWE-400: Uncontrolled Resource Consumption [-Link-](https://cwe.mitre.org/data/definitions/400.html)
* Description
The product does not properly control the allocation and maintenance of a limited resource, thereby enabling an actor to influence the amount of resources consumed, eventually leading to the exhaustion of available resources.

* Files Analyzed
   * FileContentProvider.java [-Link-](https://github.com/Chepburn-uno/NextCloudAndroidScan/blob/ef2987d6dd7b292296b338ac3e038cea9aedcf12/app/src/main/java/com/owncloud/android/providers/FileContentProvider.java#L132)

* Automated Scan
   * SNYK Code Scanning [-Link-](https://snyk.io/)
   * [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=4f95a74d-8b1a-4037-bb5a-182fe4b8d65b&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)
 
  ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/CWE%20400.png)
* Code Summary Review
Code Summary Review will go here.....

### CWE-547: Use of Hard-coded, Security-relevant Constants [-Link-](https://cwe.mitre.org/data/definitions/547.html)
* Description
The product uses hard-coded constants instead of symbolic names for security-critical values, which increases the likelihood of mistakes during code maintenance or security policy change.

* Files Analyzed
   * EncryptionUtils.java [-Link-](https://github.com/Chepburn-uno/NextCloudAndroidScan/blob/ef2987d6dd7b292296b338ac3e038cea9aedcf12/app/src/main/java/com/owncloud/android/utils/EncryptionUtils.java#L825)
   * PushUtils.java [-Link-](https://github.com/Chepburn-uno/NextCloudAndroidScan/blob/ef2987d6dd7b292296b338ac3e038cea9aedcf12/app/src/gplay/java/com/owncloud/android/utils/PushUtils.java#L293)

* Automated Scan
   * SNYK Code Scanning [-Link-](https://snyk.io/)
   * [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=4f95a74d-8b1a-4037-bb5a-182fe4b8d65b&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)

  ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/CWE%20547.png)
* Code Summary Review
Code Summary Review will go here.....

## Lucas  
### CWE-1022: Use of Web Link to Untrusted Target with window.opener Access [-Link-](https://cwe.mitre.org/data/definitions/1022.html)
* Description
   * The web application when generating links to external sites that are not considered trustworthy and therefore out of the control of the system security. However, it cannot prevent the external sites from altering security properties of the window.opener object, such as the location property.

* Files Analyzed
   * files_sharing_tab.js [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/files_sharing_tab.js)
   * SharingInherited.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingInherited.vue)
   * SharingList.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingList.vue)
   * shares.ts [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/shares.ts)

* Analysis Method
   * After a review of the files listed above, there was no clear sign of this CWE being an active vulnerability. NextCloud cloud links it generates will be specific to each system file structure and domain its created for. This CWE would only be a problem for things like spam or phishing that did not originate from the system. 
   * Automated scan of the solution provided this CWE but there was no ability for exploit. Potentially unsafe external link [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/security/code-scanning/3)
* Summary
    * After scanning both with manual and automated scans, there are no apparent issues related to the CWEs that were referenced. When the code was inspected, it seems that all link-sending functionalities are appropriately implemented. If any vulnerabilities exist they are external to the system. 


### CWE-836: Use of Password Hash Instead of password for Authentication [-Link-](https://cwe.mitre.org/data/definitions/836.html)
* Description
   * The product records password hashes in a data store, receives a hash of a password from a client, and compares the supplied hash to the hash obtained from the data store.

* Files Analyzed
   * LoginData.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/Login/LoginData.php)
   * WebAuthnChain.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/Login/WebAuthnChain.php)
   * Store.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/LoginCredentials/Store.php)
   * Credentials.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/LoginCredentials/Credentials.php)
   * AccountProperty.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Accounts/AccountProperty.php)
   * CredentialRepository.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/WebAuthn/CredentialRepository.php)

* Analysis Method
   * After an examination of the files, there is no evident indication that this CWE poses an active vulnerability. The authentication mechanisms in NextCloud include front-end validation and password verification steps that appear to effectively thwart password hash authentication of this nature. Additionally, there were no automated scan findings associated with this CWE. 

* Summary 
   * After an examination of the files, there is no indication that this CWE presents an active vulnerability. The authentication mechanisms in NextCloud include front-end validation and password verification steps that appear to be effective in preventing password hash authentication. There were no automated scan findings associated with this CWE.  

## Henri 
### CWE-200: Exposure of Sensitive Information to an Unauthorized Actor [-Link-](https://cwe.mitre.org/data/definitions/200.html)
* Description
  * The product exposes sensitive information to an actor that is not explicitly authorized to have access to that information.
    
* Files Analyzed
   * ‎OC_Files.php [-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/lib/private/legacy/OC_Files.php#L244)
   * ‎lib/base.php [-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/lib/base.php#L744)
   * cron.php [-Link-](https://github.com/hallou225/nc-server/blob/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/cron.php#L189)
   * ‎Sharing.php [-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/build/integration/features/bootstrap/Sharing.php#L344)

* Automated Scan
   * SNYK Code Scanning [-Link-](https://snyk.io/)
   * [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=a501f469-78e3-414e-9168-40631556bbf0&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)
    ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/CWE-200.png)

### CWE-611: Improper Restriction of XML External Entity Reference [-Link-](https://cwe.mitre.org/data/definitions/611.html)
* Description
  * The product processes an XML document that can contain XML entities with URIs that resolve to documents outside of the intended sphere of control, causing the product to embed incorrect documents into its output.

* Files Analyzed
   * InfoParser.php [-Link Line66-](https://github.com/hallou225/nc-server/blob/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/lib/private/App/InfoParser.php#L66)
   * ‎InfoParser.php [-Link Line69-](https://github.com/hallou225/nc-server/blob/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/lib/private/App/InfoParser.php#L69)

* Automated Scan
   * SNYK Code Scanning [-Link-](https://snyk.io/)
   * [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=a501f469-78e3-414e-9168-40631556bbf0&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)
    ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/CWE-611.png)
* Code Summary Review
* 
### CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting') [-Link-](https://cwe.mitre.org/data/definitions/79.html)
* Description
  * The product does not neutralize or incorrectly neutralizes user-controllable input before it is placed in output that is used as a web page that is served to other users.

* Files Analyzed
   * download.php [-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/apps/files/ajax/download.php#L77)
   * ‎files.js [-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/apps/files/js/files.js#L109)
   * ‎settings-admin.js[-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/apps/federation/js/settings-admin.js#L104)

* Automated Scan
   * SNYK Code Scanning [-Link-](https://snyk.io/)
   * [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=a501f469-78e3-414e-9168-40631556bbf0&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)
    ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/CWE-79.png)
* Code Summary Review


Code Summary Review will go here.....

### Tyler  
### [CVE-295: Improper Certificate Validation](https://cwe.mitre.org/data/definitions/295.html)
- **Files Analyzed**
  - Certificate.php
  - CertificateManager.PHP
  - ICertificate.php
  - ICertificateManager.php
  - ImportCertificate.php
- **Analysis Method**
  - Scanned with CodeQOL within Github and with SonarQube.  Manually Scanned within SonarQube.
- **Summary**
  - From the Scanning within both systems there didn't seem to be any issues present for the CWE.  Looking through the code it appears that all of the Certificate data is properly imported and validated.  Certificates do not appear to be available in anyway to be tampered with and are held seperately from the application itself.

### [CVE-918: Server-Side Forgery Request](https://cwe.mitre.org/data/definitions/918.html)
- **Files Analyzed**
  - DnsPinMiddleware.php
  - LocalAddressChecker.php
  - ip-lib.php
- **Analysis Method**
  - Scanned with CodeQOL within Github and with SonarQube.  Manually Scanned within SonarQube.
- **Summary**
  - From the Scanning within both systems there didn't seem to be any issues present for the CWE.  Did some searching online and found a CVE for this particular weakness from 2022.  Did a review of what was done to remedy the issue.

## Automated Code Review Applications Used

### [SNYK Code Scanning](https://snyk.io/)

Screenshot of a high level code anaylsis of SNYK scan on the NextCloud Android app on GitHub

[-Link to Scan Results-](https://app.snyk.io/invite/link/accept?invite=4f95a74d-8b1a-4037-bb5a-182fe4b8d65b&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)

![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/SNYK%20Mobile.png)

### [SpotBugs Code Scanning](https://spotbugs.github.io/)

Screenshot of a high level code anaylsis of SpotBugs scan on the NextCloud Android app on GitHub

[-Link to Scan Results-](https://www.kaminsky.me/nc-dev/android-findbugs/master.html)

![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/spotbugs%20mobile.png)

### [SonarQube](https://www.sonarsource.com/products/sonarqube/)
A code analysis tool that specializes in web applications.  It is run locally and isn't a cloud source

## Manual Code Review

## Findings Summary

## Contributions
Our team met several times during the week of the assignment to ensure the tasks were completed on time. Meeting before and after the instructor meeting to ensure that we had a good understanding of the assignment requirements. There was some initial confusion over the exact requirements of the assignment, but after clarification from the professor it was discussed and remedied. With the information from the professor about how to conduct the proper code review and work with CWEs, the group worked together to ensure that the assignment could be completed per the requirements. Once the requirements were realized the team evenly divided the workload and completed it to the satisfaction of the group. As mentioned in previous weeks we worked through our tasks in GitHub, and everyone completed their tasks. The group met again prior to turning in the assignment after all parts were compiled to ensure that nothing as missing. The team will continue to collaborate and get assignments completed together as we have in the past.


