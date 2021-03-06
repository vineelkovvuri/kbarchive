---
layout: page
title: "Q197085: Heap Corruptions Cause Access Violations in SNA Server and SnaBa"
permalink: /kb/197/Q197085/
---

## Q197085: Heap Corruptions Cause Access Violations in SNA Server and SnaBa

{% raw %}

	Article: Q197085
	Product(s): Microsoft SNA Server
	Version(s): WINDOWS:3.0,4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 13-JUN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft SNA Server, versions 3.0, 3.0 SP1, 3.0 SP2, 3.0 SP3, 4.0, 4.0 SP1 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	SNA Server and SnaBase services encounter access violations because of a problem
	with application heap corruption.
	
	CAUSE
	=====
	
	The application heap corruption occurs when a client application sends an
	invalid message to the server. The memory block the heap code is processing has
	been overwritten with some invalid data. The Windows NT heap code uses these
	size fields to traverse up and down the heap lists, if the fields contain
	garbage, the result is a trap. SNA Server does not check for any invalid
	messages from the TCP/IP transport DLLs receive buffers.
	
	RESOLUTION
	==========
	
	SNA Server 3.0
	--------------
	
	To resolve this problem, obtain the latest service pack for SNA Server version
	3.0. For additional information, please see the following article in the
	Microsoft Knowledge Base:
	
	  Q219049 How to Obtain SNA Server Version 3.0 Service Pack 4
	
	
	
	SNA Server 4.0
	--------------
	
	This problem was corrected in the latest SNA Server version 4.0 U.S. Service
	Pack. For information on obtaining this Service Pack, query on the following
	word in the Microsoft Knowledge Base (without the spaces):
	
	S E R V P A C K
	
	The RESOLUTION section above states whether this fix is available as a hotfix or
	in the latest service pack. For comparison/testing purposes, the original hotfix
	is available on http://hotfix with the following file attributes:
	
	File Name     Date       Time
	-----------------------------
	
	Snaip.dll 8/26/98 8:32AM
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft SNA Server versions
	3.0 and SNA Server version 4.0. This problem was first corrected in SNA Server
	3.0 Service Pack 4.
	
	MORE INFORMATION
	================
	
	SNA Server now checks the size of all incoming TCP/IP messages. If it's larger
	than allowed, SNA Server will disregard the message and close the client
	connection. Event ID 631 will be logged in the Windows NT Application event
	viewer with the IP Address of the client.
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbSNAServSearch kbSNAServ300 kbSNAServ400 kbSNAServ300SP3 kbSNAServ300SP1 kbSNAServ400SP1 kbSNAServ300SP2
	Version           : WINDOWS:3.0,4.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
