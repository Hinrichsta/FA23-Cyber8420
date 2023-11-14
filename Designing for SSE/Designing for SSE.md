# Data Flow Diagrams  

## DFD Level 2 Report
[Nextcloud Server DFD Report](https://htmlpreview.github.io/?https://github.com/Hinrichsta/FA23-Cyber8420/blob/main/Designing%20for%20SSE/NextCloudServer_TMT_Report.htm)  
![Threat Model](./Threat%20Model.png)  


# Introduction
Our data flow diagram combines each team members level 0 DFD's which we combined into a level 2 DFD. In this single diagram we show the user flow within the Nextcloud environment, with a user accessing a file within the system. We also show an external entity being the user, accessing the Nextcloud interface via Apache or utilizing the android mobile application. We go from the Apache interface that controls web encryption and communication into the Nextcloud server itself. From the Nextcloud server we access the database and the file storage location. All of this is dependent on the authentication sources that the database connects to and the multifactor authentication for those accounts.

# Observations  
NextCloud Server 1.0 will require appropriate security testing, code reviews, update management, patch management, and change management processes and procedures. This will ensure proper implementation and help to prevent gaps when making changes to the Server. With proper logging through SIEM, implementation of Web Application Firewalls, Network Segmentation, and a proper incident response plan, the NextCloud File System will need to have external protections to help mitigate these threats. Other potential gaps are for load balancing a larger implementation would require an external system and could introduce more complexity and overhead.  High availabity would also be needed to ensure twenty four by seven uptime. The SIEM would need to have filters and ingestion mechanisms to ensure properly formatted and displayed logs. SIEM would also be backed up regularly to ensure integrity of log files ingested. Backups in general will be a critical step in ensuring reliability and integrity of data for the entire system and external systems. 

# Reflection  
This week’s assignment regarding threat modeling went very well.  We were able to meet three times this week, once with Dr. Gandhi. The first time we met was to talk out the assignment and understand what was needed for the discussion with Dr. Gandhi.  Our discussion with Dr. Gandhi lead to a quick post meeting huddle where we worked together to create a level 2 threat model together and combining each persons level 0 threat model.  We met again Friday to finalize what each member would need to accomplish before the following Monday. Our team works very well together as always and we didn’t have any issues in completing the assignment as at this point, we have a workflow that works for all of us.  

[Project Page](https://github.com/users/Hinrichsta/projects/2)
