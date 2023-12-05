# Code Review

## Introduction

Our team decided to take a scenario-based approach.  We felt this would be wise as we had one team member who focused primarily on the NextCloud mobile app which was its own repo within GitHub.  In researching the MITRE website for inline CWE’s 400 and 547 seemed feasible and potentially obtainable by an attacker. The other three team members focused on the larger overarching NextCloud server application repo on GitHub.  This is tied into file access, website access and database access, all within our original misuse case. They focused on the CWE’s 89, 79, 836, 295, 918.

## Code Review Strategy  
We decided to utilize 2 different automated code review tools for reviewing each of our CWEs so that we could cross reference and make sure potential issues were caught.  Manual reviews were then used to verify that the CWEs were not present within the application.  For the both the Server and the Mobile app they were reviewed with CodeQOL which is built into GitHub.  For the server it was secondarily reviews by Sonar Graph which is good for web applications, and the Mobile app was reviewed by Snyk and SpotBug which were better for Java applications.  Once the tools were run the found Weaknesses were reviewed to check against the ones we were looking for, failing that the manual review would be performed.

## Reviewed CWEs

* CWE-79
* CWE-89
* CWE-295
* CWE-400
* CWE-547
* CWE-836
* CWE-918
* CWE-1022

### [CWE-79: Improper Neutralization of Input During Web Page Generation ('Cross-site Scripting')](https://cwe.mitre.org/data/definitions/79.html)
- **Description**
  * The product does not neutralize or incorrectly neutralizes user-controllable input before it is placed in output that is used as a web page that is served to other users.
- **Files Analyzed**
   * download.php [-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/apps/files/ajax/download.php#L77)
   * ‎files.js [-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/apps/files/js/files.js#L109)
   * ‎settings-admin.js[-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/apps/federation/js/settings-admin.js#L104)
- **Analysis Method**
  - Automated scan of the nextcloud repo conducted via [SNYK code Scanning](https://snyk.io/).
   [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=a501f469-78e3-414e-9168-40631556bbf0&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)
    ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/CWE-79.png)
- **Code Summary Review**
   - The weakness occurs when software does not perform or incorrectly performs neutralization of input data before displaying it in user's browser.

### [CWE-89: Improper Neutralization of Special Elements used in an SQL Command ('SQL Injection')](https://cwe.mitre.org/data/definitions/89.html)
- **Description**
  - The product does not neutralize or incorrectly neutralizes user-controllable input before it is placed in output that is used as a web page that is served to other users.
- **Files Analyzed**
   - index.php [-Link-](https://github.com/hallou225/nc-server/blob/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/index.php)
   - Cache.php [-Link-](https://github.com/hallou225/nc-server/blob/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/lib/private/Files/Cache/Cache.php).
   - ‎Sharing.php [-Link-](https://github.com/hallou225/nc-server/blob/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/build/integration/features/bootstrap/Sharing.php).
   - SFTP.php [-Link-](https://github.com/hallou225/nc-server/tree/0f4e4baebcfa0345ebec66ea5e78e835fd62c4eb/apps/files_external/lib/Lib/Storage/SFTP.php)
- **Analysis Method**
   - A thorough manual analysis of the files within github. Also scan github repo with [SNYK code Scanning](https://snyk.io/).
- **Code Summary Review**
   - CWE-89 represent a major security risk for application such as nexcloud. It is therefore a great relief to see that both the manual and automated scan could not validate its presence within the application. 

### [CWE-295: Improper Certificate Validation](https://cwe.mitre.org/data/definitions/295.html)
- **Description**
  - The product does not validate, or incorrectly validates, a certificate.
- **Files Analyzed**
  - Certificate.php  [-Link-](https://github.com/nextcloud/server/blob/ca60df9abdd5b4b65d1d48289c82aea3f982b2a3/lib/private/Security/Certificate.php)
  - CertificateManager.PHP  [-Link-](https://github.com/nextcloud/server/blob/ca60df9abdd5b4b65d1d48289c82aea3f982b2a3/lib/private/Security/CertificateManager.php)
  - ICertificate.php [-Link-](https://github.com/nextcloud/server/blob/ca60df9abdd5b4b65d1d48289c82aea3f982b2a3/lib/public/ICertificate.php)
  - ICertificateManager.php [-Link-](https://github.com/nextcloud/server/blob/ca60df9abdd5b4b65d1d48289c82aea3f982b2a3/lib/public/ICertificateManager.php)
  - ImportCertificate.php [-Link-](https://github.com/nextcloud/server/blob/ca60df9abdd5b4b65d1d48289c82aea3f982b2a3/core/Command/Security/ImportCertificate.php)
- **Analysis Method**
  - Scanned with CodeQOL within Github and with SonarQube.  Manually Scanned within SonarQube.
- **Code Summary Review**
   - From the Scanning within both systems there didn't seem to be any issues present for the CWE.  Looking through the code it appears that all of the Certificate data is properly imported and validated.  Certificates do not appear to be available in anyway to be tampered with and are held seperately from the application itself.
  
 
###  [CWE-400: Uncontrolled Resource Consumption](https://cwe.mitre.org/data/definitions/400.html)
- **Description**
The product does not properly control the allocation and maintenance of a limited resource, thereby enabling an actor to influence the amount of resources consumed, eventually leading to the exhaustion of available resources.
- **Files Analyzed**
  -FileContentProvider.java [-Link-](https://github.com/Chepburn-uno/NextCloudAndroidScan/blob/ef2987d6dd7b292296b338ac3e038cea9aedcf12/app/src/main/java/com/owncloud/android/providers/FileContentProvider.java#L132)
- **Analysis Method**
   - Automated Scan conducted with [SNYK code scanning](https://snyk.io/)
   - [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=4f95a74d-8b1a-4037-bb5a-182fe4b8d65b&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)
 
  ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/CWE%20400.png)
- **Code Summary Review**
When scanning the NextCloud Android fork with Snyk and SpotBugs I picked up five hits in Snyk for CWE 400 – Regular expression injection.  All 5 hits were in the file, “FileContentProvider.java” for the lines below.  However, in the scan output there is the caveat that depending upon the programing this “may” result in a Regular Expression Injection vulnerability that could lead to a Denial of Service attack.

1 - VerificationUtils.verifyWhere(selection);

2 - VerificationUtils.verifyWhere(where);

3 - result = query(db, uri, projection, selection, selectionArgs, sortOrder);

4 - VerificationUtils.verifySortOrder(sortOrder);

### [CWE-547: Use of Hard-coded, Security-relevant Constants](https://cwe.mitre.org/data/definitions/547.html)
- **Description**
 - The product uses hard-coded constants instead of symbolic names for security-critical values, which increases the likelihood of mistakes during code maintenance or security policy change.
- **Files Analyzed**
   * EncryptionUtils.java [-Link-](https://github.com/Chepburn-uno/NextCloudAndroidScan/blob/ef2987d6dd7b292296b338ac3e038cea9aedcf12/app/src/main/java/com/owncloud/android/utils/EncryptionUtils.java#L825)
   * PushUtils.java [-Link-](https://github.com/Chepburn-uno/NextCloudAndroidScan/blob/ef2987d6dd7b292296b338ac3e038cea9aedcf12/app/src/gplay/java/com/owncloud/android/utils/PushUtils.java#L293)

- **Analysis Method**
   * SNYK Code Scanning [-Link-](https://snyk.io/)
   * [-Link to Full Scan Results-](https://app.snyk.io/invite/link/accept?invite=4f95a74d-8b1a-4037-bb5a-182fe4b8d65b&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)

  ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/CWE%20547.png)
- **Code Summary Review**
   - When scanning the NextCloud Android fork with Snyk and SpotBugs I picked up four hits in Snyk for CWE 547 – Hardcoded Secret.  For this CWE I had two in the file PushUtils.java and two in EncryptionUtils.java. which had the effected coding lines below.  All four hits call the coder to use java.security.SecureRandom to generate strong random cryptographic numbers.

EncryptionUtils.java 

1 - X509EncodedKeySpec keySpec = new X509EncodedKeySpec(bytes);

2 - PKCS8EncodedKeySpec keySpec = new PKCS8EncodedKeySpec(bytes);

java.security.SecureRandom

1 - GCMParameterSpec spec = new GCMParameterSpec(128, iv);

2 -KeySpec spec = new PBEKeySpec(keyPhrase.toCharArray(), salt, iterationCount, keyStrength);

### [CWE-836: Use of Password Hash Instead of password for Authentication](https://cwe.mitre.org/data/definitions/836.html)
- **Description**
   * The product records password hashes in a data store, receives a hash of a password from a client, and compares the supplied hash to the hash obtained from the data store.

- **Files Analyzed**
   * LoginData.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/Login/LoginData.php)
   * WebAuthnChain.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/Login/WebAuthnChain.php)
   * Store.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/LoginCredentials/Store.php)
   * Credentials.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/LoginCredentials/Credentials.php)
   * AccountProperty.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Accounts/AccountProperty.php)
   * CredentialRepository.php [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/lib/private/Authentication/WebAuthn/CredentialRepository.php)

- **Analysis Method**
   * After an examination of the files, there is no evident indication that this CWE poses an active vulnerability. The authentication mechanisms in NextCloud include front-end validation and password verification steps that appear to effectively thwart password hash authentication of this nature. Additionally, there were no automated scan findings associated with this CWE. 

- **Code Summary Review**
   - After an examination of the files, there is no indication that this CWE presents an active vulnerability. The authentication mechanisms in NextCloud include front-end validation and password verification steps that appear to be effective in preventing password hash authentication. There were no automated scan findings associated with this CWE.
     
 ### [CWE-918: Server-Side Forgery Request](https://cwe.mitre.org/data/definitions/918.html)
- **Description**
   * The web server receives a URL or similar request from an upstream component and retrieves the contents of this URL, but it does not sufficiently ensure that the request is being sent to the expected destination.
- **Files Analyzed**
  - DnsPinMiddleware.php [-Link-](https://github.com/nextcloud/server/blob/ca60df9abdd5b4b65d1d48289c82aea3f982b2a3/lib/private/Http/Client/DnsPinMiddleware.php#L4) 
- **Analysis Method**
  - Scanned with CodeQOL within Github and with SonarQube.  Manually Scanned within SonarQube.
- **Code Summary Review**
   - From the Scanning within both systems there didn't seem to be any issues present for the CWE.  Did some searching online and found a CVE for this particular weakness from 2022.  Did a review of what was done to remedy the issue.

 
### [CWE-1022: Use of Web Link to Untrusted Target with window.opener Access](https://cwe.mitre.org/data/definitions/1022.html)
- **Description**
   * The web application when generating links to external sites that are not considered trustworthy and therefore out of the control of the system security. However, it cannot prevent the external sites from altering security properties of the window.opener object, such as the location property.

* Files Analyzed
   * files_sharing_tab.js [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/files_sharing_tab.js)
   * SharingInherited.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingInherited.vue)
   * SharingList.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingList.vue)
   * shares.ts [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/shares.ts)

- **Analysis Method**
   * After a review of the files listed above, there was no clear sign of this CWE being an active vulnerability. NextCloud cloud links it generates will be specific to each system file structure and domain its created for. This CWE would only be a problem for things like spam or phishing that did not originate from the system. 
   * Automated scan of the solution provided this CWE but there was no ability for exploit. Potentially unsafe external link [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/security/code-scanning/3)
- **Code Summary Review**
   - After scanning both with manual and automated scans, there are no apparent issues related to the CWEs that were referenced. When the code was inspected, it seems that all link-sending functionalities are appropriately implemented. If any vulnerabilities exist they are external to the system. 














## Automated Code Review Applications Used

### [SNYK Code Scanning](https://snyk.io/)
  #### NextCloud Android App on Github
Screenshot of a high level code anaylsis of SNYK scan on the NextCloud Android app on GitHub
[-Link to Scan Results-](https://app.snyk.io/invite/link/accept?invite=4f95a74d-8b1a-4037-bb5a-182fe4b8d65b&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)

![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/SNYK%20Mobile.png)
  #### NextCloud Server on Github
  Screenshot of a high level code analysis of SNYK scan on the NextCloud Server app on Github
  [-Link to Scan Results-](https://app.snyk.io/invite/link/accept?invite=a501f469-78e3-414e-9168-40631556bbf0&utm_source=link_invite&utm_medium=referral&utm_campaign=product-link-invite&from=link_invite)
  ![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/SNYK%20NextCloud%20Server.png)
  

### [SpotBugs Code Scanning](https://spotbugs.github.io/)

Screenshot of a high level code anaylsis of SpotBugs scan on the NextCloud Android app on GitHub

[-Link to Scan Results-](https://www.kaminsky.me/nc-dev/android-findbugs/master.html)

![](https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Code%20Review/spotbugs%20mobile.png)

### [SonarQube](https://www.sonarsource.com/products/sonarqube/)
A code analysis tool that specializes in web applications.  It is run locally and isn't a cloud source

## Findings Summary

Given out banking company we felt the scanning from the three different application code scanners were successful.  However, we did come across one CWE 475 vulnerability that would require further mobile application unit testing. We did find in the application scan CWE 79 which in proper neutralization input during webpage generation which could lead to cross site scripting. The remainder of the CWE's don't appear to affect our system and don't require any further remediation. However continued code review and testing would need to be conducted regularly. The OwnCloud CWE 2023,49103-05, NextCloud is a fork of OwnCloud and does not contain these vulnerabilites. 

## Contributions
Our team met several times during the week of the assignment to ensure the tasks were completed on time. Meeting before and after the instructor meeting to ensure that we had a good understanding of the assignment requirements. There was some initial confusion over the exact requirements of the assignment, but after clarification from the professor it was discussed and remedied. With the information from the professor about how to conduct the proper code review and work with CWEs, the group worked together to ensure that the assignment could be completed per the requirements. Once the requirements were realized the team evenly divided the workload and completed it to the satisfaction of the group. As mentioned in previous weeks we worked through our tasks in GitHub, and everyone completed their tasks. The group met again prior to turning in the assignment after all parts were compiled to ensure that nothing as missing. The team will continue to collaborate and get assignments completed together as we have in the past.


