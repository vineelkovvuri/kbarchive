---
layout: page
title: "Q183858: Ipconfig.exe Usage for MS-DOS 3.0 Network Client"
permalink: /kb/183/Q183858/
---

## Q183858: Ipconfig.exe Usage for MS-DOS 3.0 Network Client

{% raw %}

	Article: Q183858
	Product(s): Windows for Workgroups and Windows NT Networking Issues
	Version(s): WINDOWS:95;WinNT:3.0,4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 10-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 4.0 
	- Microsoft Windows 95 
	- Microsoft Network Client for MS-DOS version 3.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you use the Ipconfig.exe file from the Microsoft Network Client 3.0 for
	MS-DOS that ships with Windows NT Server 4.0, you may receive the following
	error messages:
	
	  No DHCP data available
	
	-or-
	
	  Usage: C:\Net\Ipconfig.exe <lanroot>
	
	CAUSE
	=====
	
	The Ipconfig.exe file from the Microsoft Network Client 3.0 is different from
	the version that ships with Windows for Workgroups 3.11 or the one that ships
	with Windows NT 4.0. The <lanroot> option refers to the directory where
	the networking software is installed, usually C:\Net.
	
	RESOLUTION
	==========
	
	The proper syntax for IPCONFIG in this case would be:
	
	  Ipconfig.exe C:\Net
	
	MORE INFORMATION
	================
	
	The <lanroot> variable is defined in the [network] section of the
	System.ini that is located in the directory where the client was installed.
	
	Any other switches or commands will produce one of the two error messages
	described above.
	
	NOTE: Ipconfig.exe from the Microsoft Network Client 3.0 can also be run from
	Windows 95, as long as the directory for the client still exists because the
	<lanroot> option must be entered. Another alternative for a command-line
	Ipconfig.exe in Windows 95 is to use the Ipconfig.exe from Windows for
	Workgroups 3.11.
	
	Additional query words: MSDOS WFW
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbAudDeveloper kbWin95search kbZNotKeyword kbZNotKeyword3 kbNetworkClientSearch kbNetworkClient300DOS
	Version           : WINDOWS:95;WinNT:3.0,4.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
