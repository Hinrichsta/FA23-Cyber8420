# Code Review

## Introduction

Our team decided to take a scenario-based approach.  We felt this would be wise as we had one team member who focused primarily on the NextCloud mobile app which was it's own repo within GitHub.  In researching the MITRE website for inline CWE’s 400 and 547 seemed feasible and potentially obtainable by an attacker. The other three team members focused on the larger overarching NextCloud server application repo on GitHub.  This is tied in to file access, website access and database access, all within our original misuse case. They focused on the CWE’s 200, 836, 295, 918???

## Code Review Strategy  
We decided to utilize 2 different automated code review tools for reviewing each of our CWEs so that we could cross reference and make sure potential issues were caught.  Manual reviews were then used to verify that the CWEs were not present within the application.  For the both the Server and the Mobile app they were reviewed with CodeQOL which is built into GitHub.  For the server it was secondarily reviews by Sonar Graph which is good for web applications, and the Mobile app was reviewed by Snyk and SpotBug which were better for Java applications.  Once the tools were run the found Weaknesses were reviewed to check against the ones we were looking for, failing that the manual review would be performed.

## Reviewed CWEs

* CWE-400  (Chris)
* CWE-547  (Chris)
* CWE-XXX  (Henri)
* CWE-200  (Henri)
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
•	Description 
  o	The web application generates links to external sites that are not considered trustworthy and fall beyond its control. However, it fails to adequately restrict the ability of these external sites to alter essential security properties of the window.opener object, such as the location property.


* Files Analyzed
   * files_sharing_tab.js [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/files_sharing_tab.js)
   * SharingInherited.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingInherited.vue)
   * SharingList.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingList.vue)
   * shares.ts [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/shares.ts)

•	Analysis Method
  o	After a review of the files listed above, there was no clear sign of this CWE being an active vulnerability. NextCloud cloud links it generates will be specific to each system file structure and domain its created for. This CWE would only be a problem for things like spam or phishing that did not originate from the system. 
  o	Automated scan of the solution provided this CWE but there was no ability for exploit. Potentially unsafe external link -Link-
•	Summary
  o	Upon scanning both systems, no apparent issues related to the CWE were detected. Upon code inspection, it seems that all link-sending functionalities are appropriately implemented, and vulnerabilities, if any, exist externally to the system. Links generated by this system lack mechanisms for tampering, preventing the inclusion of invalid URLs or external domains. Additionally, employing proxies in this system can enhance link security.


### CWE-836: Use of Password Hash Instead of password for Authentication [-Link-](https://cwe.mitre.org/data/definitions/836.html)
* Description
CWE Description will go here.....

* Files Analyzed
   * placeholder [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/files_sharing_tab.js)
   * placeholder [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingInherited.vue)
   * placeholder [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingList.vue)
   * placeholder [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/shares.ts)

* Automated Scan
   * Nothing in automated scan was related to this CWE. 

* Code Summary Review
Code Summary Review will go here.....

## Henri 
### CWE-xxx: CVE Name [-Link-](https://cwe.mitre.org/data/definitions/400.html)
* Descriptio
The product does n

* Files Analyzed
   * FileContentProvider.java [-Link-](https://github.com/Chepburn-uno/NextCloudAndroidScan/blob/ef2987d6dd7b292296b338ac3e038cea9aedcf12/app/src/main/java/com/owncloud/android/providers/FileContentProvider.java#L132)

* Automated Scan
   * SNYK Code Scanning [-Link-](https://snyk.io/)
   * [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=a501f469-78e3-414e-9168-40631556bbf0&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)

### CWE-xxx: CVE Name [-Link-](https://cwe.mitre.org/data/definitions/400.html)
* Descriptio
The product does n

* Files Analyzed
   * FileContentProvider.java [-Link-](https://github.com/Chepburn-uno/NextCloudAndroidScan/blob/ef2987d6dd7b292296b338ac3e038cea9aedcf12/app/src/main/java/com/owncloud/android/providers/FileContentProvider.java#L132)

* Automated Scan
   * SNYK Code Scanning [-Link-](https://snyk.io/)
   * [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=a501f469-78e3-414e-9168-40631556bbf0&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)

  ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/CWE%20400.png)
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


