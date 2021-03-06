---
layout: page
title: "Q164792: CPU Use at 100 Percent with SNA Server 3.0 Print Server"
permalink: /kb/164/Q164792/
---

## Q164792: CPU Use at 100 Percent with SNA Server 3.0 Print Server

{% raw %}

	Article: Q164792
	Product(s): Microsoft SNA Server
	Version(s): WINDOWS:3.0; winnt:3.51,4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 13-JUN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft SNA Server, version 3.0 
	- the operating system: Microsoft Windows NT, versions 3.51, 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When using SNA Server 3.0 on Windows NT Server 3.51 or 4.0, the CPU use may
	reach 100 percent and stay at this value indefinitely. This problem has only
	been observed by using SNA Server 3.0's print server, where the local print
	processor is not spooling data in a RAW format to a destination print server.
	You can observe this CPU use by going into Performance Monitor and looking at
	the following counters:
	
	  Object: Processor
	  Instance: 0
	  Counter: % Processor Time
	
	  Object: Process
	  Instance: snaprint
	  Counter: % Processor Time
	
	You will see the first counter at 100 percent and the second counter between 97
	to 100 percent indefinitely.
	
	CAUSE
	=====
	
	The cause of this problem is currently being investigated.
	
	
	WORKAROUND
	==========
	
	You can use a workaround until a fix can be made to the Windows NT Server print
	subsystem. The workaround is to make sure that the print job from SNA Server is
	spooled as a RAW datatype to the destination print server. You can accomplish
	this by doing either of the following:
	
	- On a Windows NT Server 4.0 client (where SNA Server is running), go into the
	  Properties for the defined printer. Click the Print Processor button and
	  check the "Always spool RAW datatype" check box. By default, this option is
	  not checked.
	
	- On a Windows NT Server 3.51 client (where SNA Server is running), select the
	  printer in Print Manager, click Properties on the Printer menu, and click
	  Details. The default datatype needs to be RAW. By default under Windows NT
	  Server 3.51, the default datatype is RAW.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT Server 3.51 and 4.0
	and SNA Server 3.0. This problem was corrected in the latest Microsoft SNA
	Server 3.0 U.S. Service Pack. For information on obtaining the service pack,
	query on the following word in the Microsoft Knowledge Base (without the
	spaces):
	
	  S E R V P A C K
	
	Additional query words: prodnt prodsna sna30
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbOSWinSearch kbOSWinNT400 kbOSWinNT351 kbSNAServSearch kbSNAServ300 kbOSWinNTSearch
	Version           : WINDOWS:3.0; winnt:3.51,4.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
