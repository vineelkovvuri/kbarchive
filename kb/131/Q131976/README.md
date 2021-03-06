---
layout: page
title: "Q131976: How to Disable Detection of Devices on Serial Ports"
permalink: /kb/131/Q131976/
---

## Q131976: How to Disable Detection of Devices on Serial Ports

{% raw %}

	Article: Q131976
	Product(s): Microsoft Windows NT
	Version(s): WinNT:3.1,3.5,3.51,4.0
	Operating System(s): 
	Keyword(s): kbusage
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 3.1 
	- Microsoft Windows NT Workstation version 3.1 
	- Microsoft Windows NT Advanced Server, version 3.1 
	- Microsoft Windows NT Workstation versions 3.5, 3.51, 4.0 
	- Microsoft Windows NT Server versions 3.5, 3.51, 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article explains how to modify the Boot.ini file to disable the detection
	of devices on COM ports.
	
	When you start Windows NT, NTDETECT searches for the pointing device (usually a
	mouse). In the course of this process, data is sent to the serial (COM) ports.
	If a serial mouse is detected, Windows NT disables the port so a device driver
	for the mouse can load instead. If a device is not detected, Windows NT disables
	the port. A disabled COM port does not display any information in Control Panel
	Ports.
	
	
	MORE INFORMATION
	================
	
	To disable the detection of devices on COM ports in Windows NT:
	
	1. Make a backup copy of the Boot.ini file.
	
	2. Remove the hidden, system, and read-only attributes from the Boot.ini file.
	
	3. Using a text editor (such as Notepad) open the Boot.ini file.
	
	4. Add the /NoSerialMice option to the end of each entry in the [operating
	  systems] section of Boot.ini. See the example below for more information.
	
	5. Save Boot.ini and quit Notepad.
	
	6. Restore the hidden, system, and read-only attributes to the Boot.ini file.
	
	7. Shutdown and restart Windows NT.
	
	The following is a sample of the Boot.ini file:
	
	     [boot loader]
	     timeout=3
	     default=multi(0)disk(0)rdisk(0)partition(1)\WINNT35
	
	     [operating systems]
	     multi(0)disk(0)rdisk(0)partition(1)\WINNT35="Windows NT Workstation
	        Version 3.51" /NoSerialMice
	
	     multi(0)disk(0)rdisk(0)partition(1)\WINNT35="Windows NT Workstation
	        Version 3.51 [VGA mode]" /basevideo /sos /NoSerialMice
	
	NoSerialMice Syntax
	-------------------
	
	/NoSerialMice          - Disables the detection of serial mice on
	                        all COM ports.
	
	/NoSerialMice:COMx     - Disables the detection of serial mice on
	                        COM x, where x is the number of the port.
	
	/NoSerialMice:COMx,y,z - Disables the detection of serial mice on
	                        COM x, y and z.
	
	NOTE: The /NoSerialMice option is not case sensitive.
	
	======================================================================
	Keywords          : kbusage 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT351search kbWinNT350search kbWinNT400search kbWinNTW350 kbWinNTW350search kbWinNTW351search kbWinNTW351 kbWinNTW310 kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbWinNTS351 kbWinNTS350 kbWinNTS310 kbWinNTAdvSerSearch kbWinNTAdvServ310 kbWinNTS351search kbWinNTS350search kbWinNTS310search kbWinNT310Search kbWinNTW310Search
	Version           : WinNT:3.1,3.5,3.51,4.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
