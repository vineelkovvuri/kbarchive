---
layout: page
title: "Q103818: DoubleSpace Leaves &#92;WINDOWS&#92;SPART.PAR on Host Drive"
permalink: /kb/103/Q103818/
---

## Q103818: DoubleSpace Leaves &#92;WINDOWS&#92;SPART.PAR on Host Drive

{% raw %}

	Article: Q103818
	Product(s): Microsoft Disk Operating System
	Version(s): MS-DOS:6.2,6.22
	Operating System(s): 
	Keyword(s): 
	Last Modified: 20-NOV-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft MS-DOS operating system versions 6.2, 6.22 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	This information applies to both Microsoft DoubleSpace and Microsoft DriveSpace.
	For MS-DOS 6.22, use DRVSPACE in place of DBLSPACE for commands and filenames.
	
	Under some conditions, DoubleSpace may leave the Windows directory and the file
	SPART.PAR on the host drive after compressing an existing drive.
	
	CAUSE
	=====
	
	This situation occurs when you compress the drive that contains your Windows
	directory (typically drive C), but you have your permanent swap file on a
	different drive (for example, drive D). The Windows directory is copied to the
	DoubleSpace-compressed drive, and all files and subdirectories are moved, except
	the SPART.PAR pointer file. This file is left on the host in an otherwise empty
	Windows directory.
	
	This does not cause a problem for Windows because it creates a new SPART.PAR file
	on the DoubleSpace-compressed drive.
	
	RESOLUTION
	==========
	
	You can safely delete the Windows directory on you host drive if you don't have
	any other files in the Windows directory. To do this:
	
	1. To determine which drive is your host drive, type "dblspace /list" (without
	  the quotation marks) at the MS-DOS command prompt and then press ENTER.
	
	2. Use the DIR command to determine which files are in the Windows directory on
	  the host drive. For example, type "dir h:\windows /a" (without the quotation
	  marks) at the MS-DOS command prompt and then press ENTER. The /A parameter
	  displays all hidden files.
	
	3. If the only file in your Windows directory on the host drive is SPART.PAR, or
	  if you don't need any of the files in the Windows directory, you can delete
	  the directory. To do this, use the DELTREE command. For example, type
	  "deltree h:\windows /y" (without the quotation marks) at the MS-DOS command
	  prompt and then press ENTER.
	
	NOTE: If you want to uncompress the drive that contains your Windows directory,
	and a duplicate Windows directory exists on the host drive, you will have to
	delete the Windows directory from the host drive.
	
	Additional query words: 6.20
	
	======================================================================
	Keywords          :  
	Technology        : kbMSDOSSearch kbMSDOS622 kbMSDOS620
	Version           : MS-DOS:6.2,6.22
	
	=============================================================================
	

{% endraw %}
