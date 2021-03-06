---
layout: page
title: "Q168739: XADM: Error 2182 Attempting to Start Information Store"
permalink: /kb/168/Q168739/
---

## Q168739: XADM: Error 2182 Attempting to Start Information Store

{% raw %}

	Article: Q168739
	Product(s): Microsoft Exchange
	Version(s): WinNT:4.0 5.5
	Operating System(s): 
	Keyword(s): kbusage
	Last Modified: 18-APR-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, versions 4.0, 5.5 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	The Information Store does not start. You may see one or more of the following
	symptoms:
	
	- You see Error 2182 when attempting to start Information Store.
	
	- The Microsoft Exchange Information Store service in Control Panel Services
	  status is blank, but when you attempt to start it, you get Error 2182,
	  stating "The requested services is already started."
	
	- When you attempt to stop one or more of the Microsoft Exchange services in
	  Control Panel Services, there is an error message stating "Service could not
	  be controlled in its present state."
	
	RESOLUTION
	==========
	
	To resolve this problem:
	
	1. Note startup parameters of all Microsoft Exchange Services in Control Panel
	  Services.
	
	2. Change all Microsoft Exchange Services startup parameters to Manual.
	
	3. Stop and restart the server.
	
	4. Start the services in the following order
	
	  Microsoft Exchange System Attendant
	  Microsoft Exchange Directory
	  Microsoft Exchange Information Store
	  Microsoft Exchange Message Transfer Agent,
	  Microsoft Mail Connector Interchange
	  and so on... PCMTA, Directory Sync, IMC, Schedule+ Free Busy Connector
	
	5. Change all Microsoft Exchange Services Startup parameters back to the
	  previous startup parameter prior to changing to Manual.
	
	MORE INFORMATION
	================
	
	This error may also be generated after an ungraceful shutdown of Exchange
	Server, or after the Information Store stops responding due to lack of disk
	space. After disk space is reclaimed you may also experience the above
	symptoms.
	
	For additional information, please see the following articles in the Microsoft
	Knowledge Base:
	
	  Q128325 Reclaiming Disk Space for the Information Store
	
	  Q163913 IS or DS Stops Due To Lack of Drive Space for Log Files
	
	Additional query words: crash hang
	======================================================================
	Keywords          : kbusage 
	Technology        : kbExchangeSearch kbExchange550 kbExchange400 kbZNotKeyword2
	Version           : WinNT:4.0 5.5
	
	=============================================================================
	

{% endraw %}
