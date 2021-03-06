---
layout: page
title: "Q311438: SNA Applications &quot;Hang&quot; with Event 556"
permalink: /kb/311/Q311438/
---

## Q311438: SNA Applications &quot;Hang&quot; with Event 556

{% raw %}

	Article: Q311438
	Product(s): Microsoft SNA Server
	Version(s): 4.0
	Operating System(s): 
	Keyword(s): kbDSupport sna4 kbsna400sp1 kbsna400sp2 kbsna400sp3 kbhis2000 kbhis2000bug kbsna400sp4
	Last Modified: 08-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Host Integration Server 2000 
	- Microsoft SNA Server, version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	SNA applications that are running on an SNA Client may stop responding ("hang"),
	when one of the applications requests a logical unit (LU). The following event
	may be logged in the Application Event Log when this occurs:
	
	  Event ID: 556
	  Description: A system error occurred while making a pipe connection, rc =
	  <return code>
	
	This problem occurs when there are multiple SNA applications running on the same
	system that repeatedly load and unload any of the SNA API (RUI, SLI, APPC, or
	CPI-C) dynamic link libraries (DLLs).
	
	CAUSE
	=====
	
	An internal resource that keeps track of SnaBase's active RamPipe connections
	can exceed its maximum value under certain circumstances, which causes the
	problem.
	
	RESOLUTION
	==========
	
	SNA Server 4.0
	--------------
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem described in this article and should be applied only to
	systems experiencing this specific problem. This fix may receive additional
	testing at a later time, to further ensure product quality. Therefore, if you
	are not severely affected by this problem, Microsoft recommends that you wait
	for the next Microsoft SNA Server version 4.0 service pack that contains this
	fix.
	
	To resolve this problem immediately, contact Microsoft Product Support Services
	to obtain the fix. For a complete list of Microsoft Product Support Services
	phone numbers and information about support costs, please go to the following
	address on the World Wide Web:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	NOTE: In special cases, charges that are normally incurred for support calls may
	be canceled, if a Microsoft Support Professional determines that a specific
	update will resolve your problem. Normal support costs will apply to additional
	support questions and issues that do not qualify for the specific update in
	question.
	
	The English version of this fix should have the following file attributes or
	later:
	
	+---------------------------------+
	| File name   | Date      | Time  | 
	+---------------------------------+
	| Snadmod.dll | 3/26/2001 | 11:28 | 
	+---------------------------------+
	
	NOTE: Because of file dependencies, the most recent fix that contains the above
	files may also contain additional files.
	
	
	
	Host Integration Server 2000
	----------------------------
	
	No fix is available for this problem in Host Integration Server 2000 at this
	time.
	
	WORKAROUND
	==========
	
	To avoid this problem, keep the number of concurrent SNA applications below 15
	or rewrite the applications to avoid repeatedly loading and unloading the SNA
	API DLLs.
	
	STATUS
	======
	
	SNA Server 4.0
	
	Microsoft has confirmed this to be a problem in Microsoft SNA Server version
	4.0.
	
	Host Integration Server 2000
	
	Microsoft has confirmed this to be a problem in Microsoft Host Integration Server
	2000.
	
	
	MORE INFORMATION
	================
	
	SnaBase maintains an internal table called the LPd table to track client server
	connections. This table can contain up to 255 entries. If there are multiple
	processes that repeatedly load and unload any of the SNA API DLLs, each process
	may consume as many SnaBase LPd records as there are processes. For example, if
	you have 30 processes, the total number of allocated LPds can be up to 30*30,
	which is greater than 255. How many records each process actually uses depends
	on the sequence in which they load/unload the SNA API DLLs. If the timing is
	correct each process may only use one record; if the timing is bad, each process
	can consume a lot more. There must least 15 local SNA processes in order for
	this problem to occur.
	
	
	Additional query words:
	
	======================================================================
	Keywords          : kbDSupport sna4 kbsna400sp1 kbsna400sp2 kbsna400sp3 kbhis2000 kbhis2000bug kbsna400sp4 
	Technology        : kbAudDeveloper kbSNAServSearch kbHostIntegServ2000 kbSNAServ400
	Version           : :4.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
