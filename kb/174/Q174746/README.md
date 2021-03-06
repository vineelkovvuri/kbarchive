---
layout: page
title: "Q174746: XADM: Err Msg: Unexpected NT API Error: 0xC000000D"
permalink: /kb/174/Q174746/
---

## Q174746: XADM: Err Msg: Unexpected NT API Error: 0xC000000D

{% raw %}

	Article: Q174746
	Product(s): Microsoft Exchange
	Version(s): 5.5
	Operating System(s): 
	Keyword(s): kb3rdparty kbpatch kbBug kbfix kbISS
	Last Modified: 27-JUL-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 5.5 
	-------------------------------------------------------------------------------
	
	
	SUMMARY
	=======
	
	When you use Innoculan anti-virus software on a Windows NT Server version 4.0
	Service Pack 3 (SP3) computer running Microsoft Exchange Server, the Exchange
	Directory (DS) service will not start. In the Windows NT Event Viewer
	Application log, you will see the following error:
	
	  Unexpected NT API error: 0xC000000D
	  MSExchange DS ((153) ) - 1022
	  Error -1022 has occurred (internal ID 2030149). Contact Microsoft
	  Technical Support for assistance.
	  The Microsoft Exchange Server database (EDB) could not be initialized
	  and returned error -1022. Unrecoverable error, the directory can't
	  continue.
	
	This is because Innoculan installs a file system filter that disables the JET
	engine ESE97, from addressing database files.
	
	WORKAROUND
	==========
	
	One of the two following workarounds may be used if Innoculan is installed on
	the Exchange Server.
	
	1. Uninstall Innoculan and restart the computer. Disabling the Innoculan service
	  is not sufficient.
	
	2. Install a Windows NT hotfix that been released to customers as part of the
	  roll-up hotfixes that are recommended in the readme.doc file for Microsoft
	  Exchange Server, version 5.5. These hotfixes are available at:
	
	  ftp://ftp.microsoft.com/bussys/winnt/winnt-public/fixes/usa/nt40/hotfixes-postSP3/roll-up/
	
	  Note: If you later re-install Windows NT Service Packs, you must also
	  re-install the hotfixes regardless of your responses to the Overwrite Newer
	  Files prompts during the Service Pack installation.
	
	MORE INFORMATION
	================
	
	This same error has occured with Norton NT Tools version 1.0 installed.
	Disabling the Norton service does not work, it must be removed.
	
	Omtool Fax Senior 2.5 will produce this error with an internal ID of 2030148. The
	hotfix noted above also corrects this problem.
	
	Additional query words: Innoculan
	======================================================================
	Keywords          : kb3rdparty kbpatch kbBug kbfix kbISS 
	Technology        : kbExchangeSearch kbExchange550 kbZNotKeyword2
	Version           : 5.5
	Issue type        : kbbug
	
	=============================================================================
	

{% endraw %}
