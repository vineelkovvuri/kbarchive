---
layout: page
title: "Q185625: Windows NT Client Logon Fails with EnableSecuritySignature Set"
permalink: /kb/185/Q185625/
---

## Q185625: Windows NT Client Logon Fails with EnableSecuritySignature Set

{% raw %}

	Article: Q185625
	Product(s): Microsoft Windows NT
	Version(s): WinNT:4.0
	Operating System(s): 
	Keyword(s): kbWinNT400sp4fix
	Last Modified: 10-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 4.0 
	- Microsoft Windows NT Server version 4.0 
	- Microsoft Windows NT Server version 4.0, Terminal Server Edition 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	When SMB security signatures are enabled by setting EnableSecuritySignature to 1
	on the server, a Windows NT Client logon attempt may fail. The failure will
	occur if only a Lan Manager password component is present in the Windows NT
	domain account. The following error will be returned by the client:
	
	  Invalid user name or password...
	
	CAUSE
	=====
	
	The server service performs an SMB security signature check and it fails in this
	case. When a sessionsetupandx command is being performed, the check fails. The
	server assumes that the client provides Windows NT credentials. The redirector
	is incorrectly including the LanMan security information for security signatures
	as if it were Windows NT security information.
	
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for Windows NT 4.0 or
	Windows NT Server 4.0, Terminal Server Edition. For additional information,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q152734 How to Obtain the Latest Windows NT 4.0 Service Pack
	
	
	NOTE: The redirector is dependent on the server fix to operate correctly. Rdr.sys
	must be installed on the client and Srv.sys must be used on the server to
	address this issue successfully.
	
	For additional information, please see the following article in the Microsoft
	Knowledge Base:
	
	  ARTICLE-ID: Q161372
	  TITLE : How to Enable SMB Signing in Windows NT
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT 4.0 and Windows NT
	Server 4.0, Terminal Server Edition. This problem was first corrected in Windows
	NT 4.0 Service Pack 4.0 and Windows NT Server 4.0, Terminal Server Edition
	Service Pack 4.
	
	
	======================================================================
	Keywords          : kbWinNT400sp4fix 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbNTTermServ400 kbNTTermServSearch
	Version           : WinNT:4.0
	Hardware          : ALPHA x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
