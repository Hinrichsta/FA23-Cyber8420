# Security Policy
Use this section to tell people about which versions of your project are
currently being supported with security updates.
Nextcloud Hardening and security guidance. Currently, Nextcloud does not have a security policy inforce to provide to the end user. However, Nextcloud does provide the following guidance:
Nextcloud aims to ship with secure defaults that do not need to get modified by administrators. However, in some cases some additional security hardening can be applied in scenarios were the administrator has complete control over the Nextcloud instance. This page assumes that you run Nextcloud Server on Apache2 in a Linux environment.

GFH Bank advanced computer systems allow our mission partners to adhere to both state, federal and local policies in maintaining Payment Card Industry (PCI) Data Security Standard (DSS) compliance. Other regulations GFH Bank also follow other guidelines such as Sarbanes-Oxley (SOX) act of 2002,	Gramm Leach Bliley Act and the Home Mortgage Act. This is not an all inclusive list of governance GFH Bank follows, but our business goal is to protect consumers data when making both internal and external transactions. GFH Baml mumber one goal is to ensure the industry best practices and standards are followed in our strategoc business environment.

GFH Bank security policy framework includes the General Data Protection Regulation in protecting consumers data. The GDPR policy follows the strictist governance in data protection to our consumers. Those strict standards is includes, state, local and federal regulatory compliance, security governance and implementing industries best practices is what GFH Bank a part from our financial competitors. 
Protecting the processing of customers data is the number one priority. When a credit card transaction is over the network, the goal is to ensure data transmitted is both secure and tamper proof against vulnerabilities or attacks.
“Our customers care deeply about security and so do we. Nextcloud aligns with industry standards such as Clause 14 of ISO/IEC27001-2013 and related standards.” (Nextcloud, 2023)

## Supported Versions

•	LDAP/Active Directory
•	Kerberos
•	SSO/SML 2.0
•	Two factor authentication
Public key, Private Key, Oracle 19c, MySQL, SSL, PHP 8.0
Maintainence Schedule:
28 version update is to be determined (TBD)
27	Hub 6	2023-06-13	2024-06	27.1.1 (2023-09-21)	27.1.2 (2023-10-19)
26	Hub 4	2023-03-21	2024-03	26.0.7 (2023-09-21)	26.0.8 (2023-10-19)
25	Hub 3	2022-10-19	2023-10	25.0.12 (2023-09-21)	25.0.13 (2023-10-19)
The following nextcloud versions are at the end of life (EOL):

Version code	Version name	Release date	End of life	Current version	Next version
24	Hub 3	2022-05-03	2023-04	24.0.12 (2023-04-20)	End of Life
23	Hub 2	2021-11-30	2022-12	23.0.12 (2022-12-08)	End of Life
22	Hub	2021-07-06	2022-07	22.2.10 (2022-07-18)	End of Life
21	Hub	2021-02-22	2022-02	21.0.9 (2022-02-15)	End of Life
20	Hub	2020-10-03	2021-11	20.0.14 (2021-11-11)	End of Life
19	Hub	2020-06-03	2021-06	19.0.13 (2021-07-01)	End of Life
18	Hub	2020-01-16	2021-01	18.0.14 (2021-01-27)	End of Life
17	17	2019-09-30	2020-10	17.0.10 (2020-10-08)	End of Life
16	16	2019-04-25	2020-06	16.0.11 (2020-06-04)	End of Life
15	15	2018-12-10	2019-12	15.0.14 (2019-12-19)	End of Life
14	14	2018-09-10	2019-09	14.0.14 (2019-08-15)	End of Life
13	13	2018-02-06	2019-02	13.0.12 (2019-02-28)	End of Life
12	12	2017-05-22	2018-11	12.0.13 (2018-11-22)	End of Life
11	11	2016-12-13	2018-03	11.0.8 (2018-03-15)	End of Life
10	10	2016-08-25	2017-08	10.0.6 (2017-08-07)	End of Life
9	9	2016-03-08	2017-04	9.0.58 (2017-04-24)	End of Life

## Reporting a Vulnerability
Overall, there have been 272 security vulnerabilities files found in Next Cloud from 2016 to 2023. The security vulnerabilities can be found at: Nextcloud : Security vulnerabilities, CVEs (cvedetails.com)

**CVE-2023-28999** > File encryption: Known vulnerability on Nextcloud is an open-source productivity platform. If not mitigated, a malicious server administrator can gain full access to the encrypted folder. Published 03-30-2023. Last updated 04-07-2023.  
**CVE-2023-28647** > attacker can enable IOS files app and bypass Nextcloud pin/password protection. Recommend upgrading IOS app to 4.7.0. There are no known workarounds for this vulnerability.  
**CVE-287 Improper Authentication** > Authentication method does not prove the proper identity is correct. Published 07-19-2006. Last updated 06-29-2023.
•	Install the latest software patches to the latest version. 
CVE-2023-39955 indicated the latest patch is 4.8.0 Based upon previous months, Nextcloud Security Vulnerabilities (XSS) will need updating based upon the latest recommended patch. The latest patch release was on August 10, 2023. The last update was on AugusNextcloud cross site scripting (XSS):

From 2016 to 2023, there were 33 cross site scripting (XSS) Nextcloud security vulnerabilities found. Two examples can be found on the following  CVE website: Nextcloud : Security vulnerabilities, CVEs xss, cross site scripting (cvedetails.com). 
CVE-2023-39955
Notes is a note-taking app for Nextcloud, an open-source cloud platform. Starting in version 4.4.0 and prior to version 4.8.0, when creating a note file with HTML, the content is rendered in the preview instead of the file being offered to download. Nextcloud Notes app version 4.8.0 contains a patch for the issue. No known workarounds are available.
CVE-2023-23942
he Nextcloud Desktop Client is a tool to synchronize files from a Nextcloud Server with your computer. Versions prior to 3.6.3 are missing sanitisation on qml labels which are used for basic HTML elements such as `strong`, `em` and `head` lines in the UI of the desktop client. The lack of sanitisation may allow for javascript injection. It is recommended that the Nextcloud Desktop Client is upgraded to 3.6.3. There are no known workarounds for this issue.
Remediation: Recommend upgrade Nextcloud Desktop Client to 3.6.3. There are no known workarounds for this issue

There have been 66 Nextcloud security vulnerabilities by impact types from 2016 to 2023. Those security vulnerabilities can be found in the following link: Nextcloud : Products and vulnerabilities (cvedetails.com)
For example: Log4Shell CVE-2021-4422
CVE-2021-45046 
It was found that the fix to address CVE-2021-44228 in Apache Log4j 2.15.0 was incomplete in certain non-default configurations. This could allow attackers with control over Thread Context Map (MDC) input data when the logging configuration uses a non-default Pattern Layout with either a Context Lookup (for example, $${ctx:loginId}) or a Thread Context Map pattern (%X, %mdc, or %MDC) to craft malicious input data using a JNDI Lookup pattern resulting in an information leak and remote code execution in some environments and local code execution in all environments.
Remediation:
Log4j 2.16.0 (Java 8) and 2.12.2 (Java 7) fix this issue by removing support for message lookup patterns and disabling JNDI functionality by default
CVE2021-45105
CVE-2021-45105 is a remote code execution (RCE) vulnerability that enables malicious actors to execute arbitrary Java code, taking control of a target server.
Apache Log4j2 versions 2.0-alpha1 through 2.16.0 (excluding 2.12.3 and 2.3.1) did not protect from uncontrolled recursion from self-referential lookups. This allows an attacker with control over Thread Context Map data to cause a denial of service when a crafted string is interpreted. 
Remediation:
This issue was fixed in Log4j 2.17.0, 2.12.3, and 2.3.1.
Nextcloud Security Vulnerability
Apache Log4j2 Remote Code Execution Vulnerability
CISA Recommendation:
For all affected software assets for which updates exist, the only acceptable remediation actions are: 1) Apply updates; OR 2) remove affected assets from agency networks. Temporary mitigations using one of the measures provided at https://www.cisa.gov/uscert/ed-22-02-apache-log4j-recommended-mitiga
CISA description:
Apache Log4j2 contains a vulnerability where JNDI features do not protect against attacker-controlled JNDI-related endpoints, allowing for remote code execution. 
CVE-2021-44832
Apache Log4j2 2.0-beta9 through 2.15.0 (excluding security releases 2.12.2, 2.12.3, and 2.3.1) JNDI features used in configuration, log messages, and parameters do not protect against attacker-controlled LDAP and other JNDI related endpoints. An attacker who can control log messages or log message parameters can execute arbitrary code loaded from LDAP servers when message lookup substitution is enabled. From log4j 2.15.0, this behavior has been disabled by default. From version 2.16.0 (along with 2.12.2, 2.12.3, and 2.3.1), this functionality has been completely removed. Note that this vulnerability is specific to log4j-core and does not affect log4net, log4cxx, or other Apache Logging Services projects.
Remediation:
CISA required action:
For all affected software assets for which updates exist, the only acceptable remediation actions are: 1) Apply updates; OR 2) remove affected assets from agency networks. Temporary mitigations using one of the measures provided at https://www.cisa.gov/uscert/ed-22-02-apache-log4j-recommended-mitigations
Link can be found in the following location: CVE-2021-44228 : Apache Log4j2 2.0-beta9 through 2.15.0 (excluding security releases 2.12.2, 2.12.3, and 2.3.1) JNDI features used in con (cvedetails.com)

CVE-2023-23942 | 
Based upon CVE-2023-23942
Description
The Nextcloud Desktop Client is a tool to synchronize files from a Nextcloud Server with your computer. Versions prior to 3.6.3 are missing sanitisation on qml labels which are used for basic HTML elements such as `strong`, `em` and `head` lines in the UI of the desktop client. The lack of sanitisation may allow for javascript injection. It is recommended that the Nextcloud Desktop Client is upgraded to 3.6.3. There are no known workarounds for this issue.


