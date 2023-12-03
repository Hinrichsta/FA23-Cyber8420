# Code Review

## Introduction

Our team decided to take a scenario-based approach.  We felt this would be wise as we had one team member who focused primarily on the NextCloud mobile app which was it's own repo within GitHub.  In researching the MITRE website for inline CWE’s 400 and 547 seemed feasible and potentially obtainable by an attacker. The other three team members focused on the larger overarching NextCloud server application repo on GitHub.  This is tied in to file access, website access and database access, all within our original misuse case. They focused on the CWE’s 200, 836, 1022???

## Reviewed CWEs

* CWE-400  (Chris)
* CWE-547  (Chris)
* CWE-XXX  (Henri)
* CWE-200  (Henri)
* CWE-1022 (Luke)
* CWE-836  (Luke)
* CWE-XXX  (Tyler)
* CWE-XXX  (Tyler)

### Our Potential list
https://cwe.mitre.org/data/definitions/699.html  
CWE-125: Out-of-bounds Read  
CWE-276: Incorrect Default Permissions  
CWE-295: Improper Certifcate Validation  
CWE-308: Use of Single-factor Authentication  
CWE-322: Key Exchange without Entity Authentication  
CWE-351: Insufficient Type Distinction  
CWE-419: Unprotected Primary Channel  
CWE-434: Unrestricted Upload of File with Dangerous Type  
CWE-836: Use of Password Hash Instead of password for Authentication  
CWE-862: Missing Authorization  
CWE-918: Server-Side Request Forgery  

## Chris  
### CWE-400: Use of Web Link to Untrusted Target with window.opener Access [-Link-](https://cwe.mitre.org/data/definitions/1022.html)
* Description
CWE Description will go here.....

* Files Analyzed
   * files_sharing_tab.js [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/files_sharing_tab.js)
   * SharingInherited.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingInherited.vue)
   * SharingList.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingList.vue)
   * shares.ts [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/shares.ts)

* Automated Scan
   * Potentially unsafe external link [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/security/code-scanning/3)

* Code Summary Review
Code Summary Review will go here.....

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

## Lucas  
### CWE-1022: Use of Web Link to Untrusted Target with window.opener Access [-Link-](https://cwe.mitre.org/data/definitions/1022.html)
* Description
CWE Description will go here.....

* Files Analyzed
   * files_sharing_tab.js [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/files_sharing_tab.js)
   * SharingInherited.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingInherited.vue)
   * SharingList.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingList.vue)
   * shares.ts [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/shares.ts)

* Automated Scan
   * Potentially unsafe external link [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/security/code-scanning/3)

* Code Summary Review
Code Summary Review will go here.....

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

## Tyler  

## Automated Code Review Applications Used

### SNYK Code Scanning [-Link-](https://snyk.io/)

Screenshot of a high level code anaylsis of SNYK scan on the NextCloud Android app on GitHub

[-Link to Scan Results-](https://app.snyk.io/invite/link/accept?invite=4f95a74d-8b1a-4037-bb5a-182fe4b8d65b&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)

![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/SNYK%20Mobile.png)

### SpotBugs Code Scanning [-Link-](https://spotbugs.github.io/)

Screenshot of a high level code anaylsis of SpotBugs scan on the NextCloud Android app on GitHub

[-Link to Scan Results-](https://www.kaminsky.me/nc-dev/android-findbugs/master.html)

![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/spotbugs%20mobile.png)

## Manual Code Review

## Findings Summary

## Contributions
Our team met several times during the week of the assignment to ensure the tasks were completed on time. Meeting before and after the instructor meeting to ensure that we had a good understanding of the assignment requirements. There was some initial confusion over the exact requirements of the assignment, but after clarification from the professor it was discussed and remedied. With the information from the professor about how to conduct the proper code review and work with CWEs, the group worked together to ensure that the assignment could be completed per the requirements. Once the requirements were realized the team evenly divided the workload and completed it to the satisfaction of the group. As mentioned in previous weeks we worked through our tasks in GitHub, and everyone completed their tasks. The group met again prior to turning in the assignment after all parts were compiled to ensure that nothing as missing. The team will continue to collaborate and get assignments completed together as we have in the past.


