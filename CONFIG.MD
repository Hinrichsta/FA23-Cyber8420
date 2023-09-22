CVE-2021-29438
The Nextcloud dialogs library (npm package @nextcloud/dialogs) before 3.1.2 insufficiently escaped text input passed to a toast. If your application displays toasts with user-supplied input, this could lead to a XSS vulnerability. The vulnerability has been patched in version 3.1.2 If you need to display HTML in the toast, explicitly pass the `options.isHTML` config flag.
Published: 2021-04-13
Updated: 2021-04-19
Nextcloud Security Vulnerabilities:
Overall, there have been 271 security vulnerabilities files found in Next Cloud from 2016 to 2023. The security vulnerabilities can be found at: Nextcloud : Security vulnerabilities, CVEs (cvedetails.com)
Nextcloud cross site scripting (XSS):
From 2016 to 2023, there were 33 cross site scripting (XSS) Nextcloud security vulnerabilities found. Two examples can be found on the following  CVE website: Nextcloud : Security vulnerabilities, CVEs xss, cross site scripting (cvedetails.com). 
CVE-2023-39955
Notes is a note-taking app for Nextcloud, an open-source cloud platform. Starting in version 4.4.0 and prior to version 4.8.0, when creating a note file with HTML, the content is rendered in the preview instead of the file being offered to download. Nextcloud Notes app version 4.8.0 contains a patch for the issue. No known workarounds are available.
CVE-2023-23942
he Nextcloud Desktop Client is a tool to synchronize files from a Nextcloud Server with your computer. Versions prior to 3.6.3 are missing sanitisation on qml labels which are used for basic HTML elements such as `strong`, `em` and `head` lines in the UI of the desktop client. The lack of sanitisation may allow for javascript injection. It is recommended that the Nextcloud Desktop Client is upgraded to 3.6.3. There are no known workarounds for this issue.
Remediation: Recommend upgrade Nextcloud Desktop Client to 3.6.3. There are no known workarounds for this issue System requirements
Webserver: 
•	Apache 2.4 with mod_php or php-fpm (recommended)
•	nginx with php-fpmWeb server configuration
•	The recommended nginx configuration changed.
PHP Runtime
•	7.4 is no longer supported
•	8.0 (deprecated)
•	8.1 (is not recommended)
•	8.2 (recommended)


