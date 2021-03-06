---
layout: page
title: "Q169614: HP DeskJet 500-Series Driver May Not Return All System Resources"
permalink: /kb/169/Q169614/
---

## Q169614: HP DeskJet 500-Series Driver May Not Return All System Resources

{% raw %}

	Article: Q169614
	Product(s): Microsoft Windows NT
	Version(s): 4.0
	Operating System(s): 
	Keyword(s): kbprint
	Last Modified: 07-SEP-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 4.0 
	- Microsoft Windows NT Workstation version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	After you print numerous jobs from Windows NT 4.0 to your Hewlett-Packard (HP)
	DeskJet 500-series printer, you may notice that your computer is running low on
	system resources. This problem may eventually lead to system instability and
	low-memory errors.
	
	CAUSE
	=====
	
	The HP DeskJet 500-series printer driver included with Windows NT 4.0 may not
	return all system resources used during a printing operation.
	
	RESOLUTION
	==========
	
	To work around this problem, reboot the computer from which you are printing.
	This reinitializes all memory and system resources used by Windows NT 4.0.
	
	STATUS
	======
	
	Microsoft is researching this problem and will post new information here in the
	Microsoft Knowledge Base as it becomes available.
	
	MORE INFORMATION
	================
	
	Total kernel memory may grow and not be fully reduced to its initial size after
	printing is completed when you are printing to an HP DeskJet 500- series
	printer. Kernel memory usage may grow slightly after one print job is completed
	and continue to grow slightly after each succeeding print job.
	
	Because the amount of kernel memory lost with each print job is relatively small
	(generally 30-40K), this issue occurs only after a very large number of print
	jobs are printed without rebooting the computer.
	
	
	To view total kernel memory, follow these steps:
	
	1. Use the right mouse button to click an empty area on the taskbar, and then
	  click Task Manager.
	
	2. Click the Performance tab. The Total value in the Kernel Memory area lists
	  the total kernel memory value.
	
	Additional query words: 500C 510 520 540 550C 560C monochrome color
	
	======================================================================
	Keywords          : kbprint 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400
	Version           : 4.0
	
	=============================================================================
	

{% endraw %}
