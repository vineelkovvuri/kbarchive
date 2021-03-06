---
layout: page
title: "Q156187: Cannot Locate Readme.doc on MSDN Compact Disc"
permalink: /kb/156/Q156187/
---

## Q156187: Cannot Locate Readme.doc on MSDN Compact Disc

{% raw %}

	Article: Q156187
	Product(s): Microsoft Windows NT
	Version(s): 4.0
	Operating System(s): 
	Keyword(s): kbusage
	Last Modified: 10-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 4.0 
	- Microsoft Windows NT Server version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you try to open Readme.doc on the Microsoft Developer Network (MSDN)
	compact disc that contains Microsoft Windows NT version 4.0, you may not be able
	to open the file as the documentation suggests.
	
	CAUSE
	=====
	
	The documentation shipped with the MSDN compact disc set that includes Microsoft
	Windows NT version 4.0 incorrectly refers to a Readme.doc file in the root
	directory that does not exist.
	
	RESOLUTION
	==========
	
	The MSDN documentation incorrectly states the filename and location of the
	preinstallation notes for Microsoft Windows NT version 4.0. The documentation
	should reference Setup.txt (uncompressed) in the directory corresponding to the
	architecture being used (for example, I386 for Intel-based hardware).
	
	Setup.txt notes preinstallation issues specific to hardware, firmware, and
	general installation topics of Microsoft Windows NT.
	
	You can find supplemental
	(http://support.microsoft.com/download/support/mslfiles/supplemental) release
	notes in Readme.wri, Network.wri, and Printer.wri. Windows NT Setup installs
	Readme.wri in the following directory:
	
	  <System Root>\System32
	
	Network.wri and Printer.wri can be found in the system root directory after
	installation.
	
	The books and manuals for Microsoft Windows NT version 4.0, including the Start
	Here manual, are organized by chapter as uncompressed .doc files and can be
	found in the Support\Books directory on the compact disc.
	
	Additional query words: setup msdn
	======================================================================
	Keywords          : kbusage 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400
	Version           : 4.0
	
	=============================================================================
	

{% endraw %}
