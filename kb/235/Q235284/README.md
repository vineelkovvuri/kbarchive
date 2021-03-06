---
layout: page
title: "Q235284: MPPE Keys Not Handled Correctly for a 128-Bit MS-CHAP Request"
permalink: /kb/235/Q235284/
---

## Q235284: MPPE Keys Not Handled Correctly for a 128-Bit MS-CHAP Request

{% raw %}

	Article: Q235284
	Product(s): Microsoft Windows NT
	Version(s): 4.0
	Operating System(s): 
	Keyword(s): kbWinNT4sp6fix
	Last Modified: 16-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 4.0, Terminal Server Edition 
	- Microsoft Windows NT Server version 4.0 
	- Microsoft Windows NT Server, Enterprise Edition version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Microsoft Point-to-Point Encryption (MPPE) keys may not be encrypted correctly
	for a 128-bit Microsoft Challenge-Handshake Authentication Protocol (MS-CHAP)
	request. The Microsoft Internet Authentication service (IAS) Remote
	Authentication Dial-In User Service (RADIUS) server and Routing and Remote
	Access Services (RRAS) correctly decrypt the MPPE keys, but do not correctly
	encrypt them.
	
	This problem occurs if a user either dials into a third-party network access
	server (such as Cisco, Ascend, and so on) and uses 128-bit MS-CHAP on the
	Windows NT 4.0 RADIUS server, or dials into a Windows NT 4.0 RRAS server that is
	configured to be authenticated on a Microsoft Windows 2000 server.
	
	RESOLUTION
	==========
	
	Windows NT Server or Workstation 4.0
	------------------------------------
	
	To resolve this problem, obtain the latest service pack for Windows NT 4.0 or the
	individual software update. For information on obtaining the latest service
	pack, please go to:
	
	- http://www.microsoft.com/Windows/ServicePacks/
	
	-or-
	
	- Q152734 How to Obtain the Latest Windows NT 4.0 Service Pack
	
	For information on obtaining the individual software update, contact Microsoft
	Product Support Services. For a complete list of Microsoft Product Support
	Services phone numbers and information on support costs, please go to the
	following address on the World Wide Web:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	
	Windows NT Server 4.0, Terminal Server Edition
	----------------------------------------------
	
	To resolve this problem, obtain the latest service pack for Windows NT Server
	4.0, Terminal Server Edition. For additional information, please see the
	following article in the Microsoft Knowledge Base:
	
	  Q152734 How to Obtain the Latest Windows NT 4.0 Service Pack
	
	
	NOTE: Another solution is available by applying the RADIUS Roll-up hotfix
	described in the following article in Microsoft Knowledge Base:
	
	  Q239864 Availability of Internet Authentication Service SP6 Rollup Hotfix
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT 4.0 and Windows NT
	Server 4.0, Terminal Server Edition.
	
	This problem was first corrected in Windows NT Server 4.0 Service Pack 6 and
	Windows NT Server 4.0, Terminal Server Edition Service Pack 6.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbWinNT4sp6fix 
	Technology        : kbWinNTsearch kbWinNT400search kbWinNTSsearch kbWinNTSEntSearch kbWinNTSEnt400 kbWinNTS400search kbWinNTS400 kbNTTermServ400 kbNTTermServSearch
	Version           : :4.0
	Hardware          : x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
