---
layout: page
title: "Q163608: XADM: SQL MS Mail Messaging Breaks After Upgrading Windows NT"
permalink: /kb/163/Q163608/
---

## Q163608: XADM: SQL MS Mail Messaging Breaks After Upgrading Windows NT

{% raw %}

	Article: Q163608
	Product(s): Microsoft Exchange
	Version(s): 4.0
	Operating System(s): 
	Keyword(s): kbinterop kbusage
	Last Modified: 09-MAY-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If you upgrade Windows NT Server from version 3.51 to version 4.0, you will no
	longer be able to send Microsoft Mail messages from a SQL Server.
	
	WORKAROUND
	==========
	
	To work around this problem, reconfigure the messaging environment with a
	computer running Microsoft Exchange Server.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft Exchange Server
	version 4.0. This problem was corrected in the latest Microsoft Exchange 4.0
	U.S. Service Pack. For information on obtaining the service pack, query on the
	following word in the Microsoft Knowledge Base (without the spaces):
	
	  S E R V P A C K
	
	MORE INFORMATION
	================
	
	You can set up SQL Server to send mail messages with Microsoft Mail 3.x. In
	Microsoft Exchange Server 4.0, you can only send a mail message through
	Microsoft Exchange Server in a SQL Server environment. If Windows NT Server 3.51
	is upgraded to Windows NT Server 4.0 with a Microsoft Mail messaging environment
	for SQL Server, new MAPI DLLs are overwritten as the Microsoft Mail client is
	upgraded to the Windows NT Server Windows Messaging System (WMS).
	
	
	
	Additional query words: MAPI
	======================================================================
	Keywords          : kbinterop kbusage 
	Technology        : kbExchangeSearch kbExchange400 kbZNotKeyword2
	Version           : 4.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
