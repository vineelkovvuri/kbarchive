---
layout: page
title: "Q299676: XADM: Event Service May Not Start with Event ID 5 Message"
permalink: /kb/299/Q299676/
---

## Q299676: XADM: Event Service May Not Start with Event ID 5 Message

{% raw %}

	Article: Q299676
	Product(s): Microsoft Exchange
	Version(s): 5.5
	Operating System(s): 
	Keyword(s): kberrmsg
	Last Modified: 11-JUN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 5.5 
	-------------------------------------------------------------------------------
	
	IMPORTANT: This article contains information about modifying the registry. Before you modify the registry, make sure to back it up and make sure that you understand how to restore the registry if a problem occurs. For information about how to back up, restore, and edit the registry, click the following article number to view the article in the Microsoft Knowledge Base:
	
	  Q256986 Description of the Microsoft Windows Registry
	
	SYMPTOMS
	========
	
	When you try to start the Microsoft Exchange Event Service, you may receive the
	following error message:
	
	  Could not start the Microsoft Exchange Event Service on Local Computer.
	  The service did not return an error. This could be an internal Windows error
	  or an internal service error.
	  If the problem persists, contact your system administrator.
	
	The following event ID message may also be logged in the Application event log:
	
	  Event Type: Error
	  Event Source: MSExchangeES
	  Event Category: General
	  Event ID: 5
	  Date: 11/01/2000
	  Time: 8:45:00 AM
	  User: N/A
	  Computer: SERVERNAME
	  Description:
	  An unexpected MAPI error occurred. Error returned was [0x80004005].
	
	CAUSE
	=====
	
	This issue can occur if the Exchange Server computer has been installed with the
	wrong organization, server or site name, or if the corresponding registry values
	have been modified from their original state.
	
	RESOLUTION
	==========
	
	WARNING: If you use Registry Editor incorrectly, you may cause serious problems
	that may require you to reinstall your operating system. Microsoft cannot
	guarantee that you can solve problems that result from using Registry Editor
	incorrectly. Use Registry Editor at your own risk.
	
	To resolve this issue if you know the correct organization, server or site name,
	modify the appropriate registry value:
	
	1. Start Registry Editor (Regedt32.exe).
	
	2. Locate the appropriate value (Enterprise, Server or Site) under the following
	  key in the registry:
	
	  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSExchangeSA\Parameters
	
	3. On the Edit menu, click String, modify the value to match the correct
	  organization (enterprise), server or site name, and then click OK.
	
	4. Quit Registry Editor.
	
	NOTE: The Exchange Server organization, server and site names are case sensitive.
	Make sure that you type the correct name and case for each value. If another
	Exchange Server computer exists in the same site, you can compare the values
	from the X500 DN registry value that is found in the following registry key:
	
	  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSExchangeMTA\Parameters
	
	
	Additional query words: mta msexchangemta event 37 script exch2kp2w
	
	======================================================================
	Keywords          : kberrmsg 
	Technology        : kbExchangeSearch kbExchange550 kbZNotKeyword2
	Version           : :5.5
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
