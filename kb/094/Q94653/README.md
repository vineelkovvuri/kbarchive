---
layout: page
title: "Q94653: Using FC.EXE to Verify CD-ROM File System Drivers"
permalink: /kb/094/Q94653/
---

## Q94653: Using FC.EXE to Verify CD-ROM File System Drivers

{% raw %}

	Article: Q94653
	Product(s): Microsoft Home Multimedia Titles
	Version(s): 1.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 25-OCT-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Multimedia Pack, version 1.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	To ensure the integrity of your files that have been copied from your CD-ROM
	drive to your hard drive, it is possible to use the MS-DOS File Compare program
	(FC.EXE) to compare the files. This test can be used to determine if the CD-ROM
	subsystem is functioning properly at the device driver or hardware level(s). It
	is a useful method for testing problems related to general protection (GP)
	faults or other critical errors that may occur while running a CD-ROM
	application with Windows such as read errors or out of memory messages.
	
	To ensure the most accurate test, use the /B (binary) switch. For example:
	
	  fc /b [drive1:][path1]filename1 [drive2:][path]filename2
	
	MORE INFORMATION
	================
	
	If the files are corrupt, check the following:
	
	- Minimize the configuration by simplifying the CONFIG.SYS and AUTOEXEC.BAT
	  files then reinstall.
	
	- Make sure Microsoft CD-ROM Extensions (MSCDEX.EXE) version 2.2 or later is
	  being used. Check the file date of the CD-ROM device driver. Check with your
	  CD-ROM drive manufacturer to see if the manufacturer has an updated device
	  driver (the *.SYS file that loads in the CONFIG.SYS file).
	
	- If you are using Windows 95 in MS-DOS mode, make sure that Mscdex.exe is
	  dated newer than 7/11/95
	
	- In Windows 95, if possible, use a protect-mode CD-ROM driver instead of
	  Mscdex. For more information, search your online help for How to Set Up
	  Hardware.
	
	- Try using the Xcopy (binary) command to copy the files from the source
	  location to the destination location then use the FC command to compare the
	  files. To use the Xcopy command, type the following at the MS-DOS command
	  prompt and press ENTER
	
	     xcopy [source] [destination]
	
	  where [source] is the path of the file you want to copy and [destination] is
	  the path to where you want to copy the file.
	
	Additional query words: multi media multimedia multi-media kbmm CD Compact Disc
	
	======================================================================
	Keywords          :  
	Technology        : kbHomeProdSearch kbHomeMMsearch kbMMPk100
	Version           : :1.0
	
	=============================================================================
	

{% endraw %}
