# Code Review

## Introduction

Our team decided to take a scenario-based approach.  We felt this would be wise as we had one team member who focused primarily on the NextCloud mobile aspect of the application which was a single repo within GitHub.  In researching the MITRE website for inline CWE’s 400 and 547 seemed feasible and potentially obtainable by an attacker. The other three team members focused on the larger overarching Nextcloud server application repo on GitHub.  This is tied in file access, website access and database access, all within our original misuse case. They focused on the CWE’s XXX???

## Reviewed CWEs

### CWE-400: Uncontrollsed Resource Consumption [-Link-](https://cwe.mitre.org/data/definitions/400.html)

Limited resources include memory, file system storage, database connection pool entries, and CPU. If an attacker can trigger the allocation of these limited resources, but the number or size of the resources is not controlled, then the attacker could cause a denial of service that consumes all available resources. This would prevent valid users from accessing the product, and it could potentially have an impact on the surrounding environment. For example, a memory exhaustion attack against an application could slow down the application as well as its host operating system.

There are at least three distinct scenarios which can commonly lead to resource exhaustion:

Lack of throttling for the number of allocated resources
Losing all references to a resource before reaching the shutdown stage
Not closing/returning a resource after processing
Resource exhaustion problems are often result due to an incorrect implementation of the following situations:

Error conditions and other exceptional circumstances.
Confusion over which part of the program is responsible for releasing the resource.

### CWE-547: Use of Hard=coded, Security-relevant Constants [-Link-](https://cwe.mitre.org/data/definitions/547.html)

If the developer does not find all occurrences of the hard-coded constants, an incorrect policy decision may be made if one of the constants is not changed. Making changes to these values will require code changes that may be difficult or impossible once the system is released to the field. In addition, these hard-coded values may become available to attackers if the code is ever disclosed.

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

## Lucas  
### CWE-1022: Use of Web Link to Untrusted Target with window.opener Access [-Link-](https://cwe.mitre.org/data/definitions/1022.html)
* Files Analyzed
   * files_sharing_tab.js [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/files_sharing_tab.js)
   * SharingInherited.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingInherited.vue)
   * SharingList.vue [-Link-](https://github.com/Hinrichsta/nextcloudserver-scan/blob/fece503fb408dc83609bfaa7003ac34593c5ba4a/apps/files_sharing/src/views/SharingList.vue)


### CWE-836: Use of Password Hash Instead of password for Authentication [-Link-](https://cwe.mitre.org/data/definitions/836.html)


## Henri  

## Tyler  

## Automated Code Review

SNYK Code Scanning [-Link-](https://snyk.io/)
![Screenshot of high level code anaylsis of SNYK scan on NextCloud Android app on GitHub](https://myoctocat.com/assets/images/base-octocat.svg)

## Manual Code Review

## Findings Summary

## Contributions
Our team met several times during the week of the assignment to ensure the tasks were completed on time. Meeting before and after the instructor meeting to ensure that we had a good understanding of the assignment requirements. There was some initial confusion over the exact requirements of the assignment, but after clarification from the professor it was discussed and remedied. With the information from the professor about how to conduct the proper code review and work with CWEs, the group worked together to ensure that the assignment could be completed per the requirements. Once the requirements were realized the team evenly divided the workload and completed it to the satisfaction of the group. As mentioned in previous weeks we worked through our tasks in GitHub, and everyone completed their tasks. The group met again prior to turning in the assignment after all parts were compiled to ensure that nothing as missing. The team will continue to collaborate and get assignments completed together as we have in the past.


