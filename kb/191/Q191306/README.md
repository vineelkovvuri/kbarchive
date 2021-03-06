---
layout: page
title: "Q191306: SMS: Unattended Installation of SMS 1.2 Service Pack 4"
permalink: /kb/191/Q191306/
---

## Q191306: SMS: Unattended Installation of SMS 1.2 Service Pack 4

{% raw %}

	Article: Q191306
	Product(s): Microsoft Systems Management Server
	Version(s): winnt:1.2
	Operating System(s): 
	Keyword(s): kbsetup kbsms200 smssetup
	Last Modified: 27-JUL-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server version 1.2 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Before Microsoft Systems Management Server version 1.2 Service Pack 4 (SP4),
	there was no method by which an administrator could apply a Systems Management
	Server Service Pack with an unattended setup option.
	
	Systems Management Server version 1.2 SP4 allows administrators to apply the
	service pack with an unattended setup.
	
	MORE INFORMATION
	================
	
	The unattended installation of Systems Management Server 1.2 SP4 performs the
	following steps:
	
	1. Stops and restarts Site Configuration Manager so that secondary sites do not
	  stop responding (hang).
	
	2. Instructs Site Configuration Manager to stop all of the services, including
	  PCMSVC32 and INVWIN32, and then shut down the site.
	
	3. Copies files as appropriate, based on whether the site server functions as a
	  secondary site server or a primary site server.
	
	4. Performs database conversion and index installation for primary sites.
	
	5. Merges the System.map file.
	
	6. Restarts the site.
	
	The unattended installation of the Service Pack does not upgrade the
	Administrator Console installation on any secondary site servers or other
	Administrator computers. Also note that the unattended installation does not
	work on the Macintosh or OS/2 clients. Upgrades to those clients must continue
	to be performed the same as they were in the past.
	
	For additional information on how to obtain Systems Management Server 1.2 Service
	Pack 4, click the article number below to view the article in the Microsoft
	Knowledge Base:
	
	  Q158864 How to Obtain Systems Management Server 1.2 Service Pack 4
	
	Additional query words: prodsms SP SP4 SCM Mac
	
	======================================================================
	Keywords          : kbsetup kbsms200 smssetup 
	Technology        : kbSMSSearch kbSMS120
	Version           : winnt:1.2
	Issue type        : kbinfo
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
