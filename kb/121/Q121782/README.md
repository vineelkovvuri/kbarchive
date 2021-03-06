---
layout: page
title: "Q121782: ADT2: Setup Wizard Cannot Find VSHARE.386 with Windows NT"
permalink: /kb/121/Q121782/
---

## Q121782: ADT2: Setup Wizard Cannot Find VSHARE.386 with Windows NT

{% raw %}

	Article: Q121782
	Product(s): Microsoft Access Distribution Kit
	Version(s): WINDOWS:2.0
	Operating System(s): 
	Keyword(s): kberrmsg kbsetup
	Last Modified: 25-JUN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Access Developer's Toolkit, version 2.0 
	-------------------------------------------------------------------------------
	
	Novice: Requires knowledge of the user interface on single-user computers.
	
	SYMPTOMS
	========
	
	When you are using the Setup Wizard to create installation disks for your custom
	application on a computer running Microsoft Windows NT, you may receive the
	following error message:
	
	  Can't find file 'C:\NT\SYSTEM\VSHARE.386'
	
	
	CAUSE
	=====
	
	VSHARE.386 is a file-locking management file included with Microsoft Access
	version 2.0. The Setup Wizard requires that this file be included on your
	application's custom Setup disks in order for your run-time application to work
	on a computer running Microsoft Windows version 3.1 or Microsoft Windows for
	Workgroups version 3.1 or 3.11. However, because Microsoft Windows NT and
	Windows 95 provide their own form of file locking, Microsoft Access Setup does
	not install the VSHARE.386 file to computers running these operating systems.
	
	RESOLUTION
	==========
	
	To work around this behavior, install the VSHARE.386 file from your original
	Microsoft Access disks to your computer's NT\SYSTEM subdirectory. To install the
	VSHARE.386 file, follow these steps:
	
	1. Copy the DECOMP.EXE file from Disk 1 of your Microsoft Access disks to your
	  Windows NT directory.
	
	2. Insert Disk 4 in a floppy drive, type the following line, and then press
	  ENTER:
	
	  DECOMP <drive>:\VSHARE.38_ <drive>:\<directory>
	
	  For example, to decompress the file from a disk in drive A to the NT\SYSTEM
	  subdirectory on drive C, you would type the following line:
	
	  DECOMP A:\VSHARE.38_ C:\NT\SYSTEM\VSHARE.386
	
	The size of the VSHARE.386 file when expanded should be 14,933.
	
	Additional query words:
	
	======================================================================
	Keywords          : kberrmsg kbsetup 
	Technology        : kbAudDeveloper kbAccessSearch kbAccessDevTK200 kbZNotKeyword3
	Version           : WINDOWS:2.0
	Hardware          : x86
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
