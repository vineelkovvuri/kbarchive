---
layout: page
title: "Q173694: Err Msg: ERROR: Setup Was Unable to Install the Boot Loader"
permalink: /kb/173/Q173694/
---

## Q173694: Err Msg: ERROR: Setup Was Unable to Install the Boot Loader

{% raw %}

	Article: Q173694
	Product(s): Microsoft Windows NT
	Version(s): 2,2.1,4.0
	Operating System(s): 
	Keyword(s): kberrmsg kbsetup
	Last Modified: 09-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 4.0 
	- Microsoft Windows NT Workstation version 4.0 
	- Microsoft Windows 95 OEM Service Release, versions 2, 2.1 
	- Microsoft Windows 98 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you start Windows NT Setup, you may receive any of the following error
	messages:
	
	   - ERROR: Setup was unable to install the Boot Loader
	
	   - ERROR: The partition you have chosen is not recognized by Windows NT
	
	   - Setup was unable to install Windows NT Boot Loader.
	
	  Ensure that your C: drive is formatted and that
	  the drive is not damaged.
	
	  Setup cannot continue. Press ENTER to exit.
	
	CAUSE
	=====
	
	Windows NT Setup does not support the FAT32 file system included with Windows 95
	OEM Service Release 2 (OSR2) or Windows 98.
	
	RESOLUTION
	==========
	
	To install Windows NT 4.0, make sure that both your boot partition and the
	partition you are installing to is either formatted with the FAT16 or NTFS file
	system, or not formatted.
	
	MORE INFORMATION
	================
	
	The FAT32 file system is a new file system option included with OSR2. OSR2
	provides support for logical drives larger than 2 gigabytes (GB). Enabling large
	disk support using the FAT32 file system is not supported by MS-DOS, the retail
	version of Windows 95, or Windows NT.
	
	NOTE: Windows NT Setup does not create or delete FAT32 partitions. Before
	deleting a partition, back up your data.
	
	For more information about the FAT32 file system or troubleshooting Windows NT
	4.0 Setup, see the following articles in the Microsoft Knowledge Base:
	
	ARTICLE-ID : Q126690
	TITLE : Windows NT 4.0 Setup Troubleshooting Guide
	
	ARTICLE-ID : Q154997
	TITLE : Description of the FAT32 File System
	
	ARTICLE-ID : Q151414
	TITLE : Win95 Partition Types Not Recognized by Windows NT
	
	
	Additional query words: win98
	
	======================================================================
	Keywords          : kberrmsg kbsetup 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbWin95search kbWin98search kbOPKSearch kbWin98 kbWin95OPKOSR2 kbWin95OPKOSR210
	Version           : :2,2.1,4.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
