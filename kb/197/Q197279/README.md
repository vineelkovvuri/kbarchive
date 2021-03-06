---
layout: page
title: "Q197279: SP4 Blue Screen Occurs on Reboot If Hardware Key Used"
permalink: /kb/197/Q197279/
---

## Q197279: SP4 Blue Screen Occurs on Reboot If Hardware Key Used

{% raw %}

	Article: Q197279
	Product(s): Microsoft Windows NT
	Version(s): WinNT:4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 27-FEB-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 4.0 
	- Microsoft Windows NT Workstation version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	After you install Windows NT 4.0 Service Pack 4 and restarting a computer that
	uses a HASP hardware key (dongle) on the parallel port for QuarkXPress or other
	proprietary software products protected by the key, a kernel mode exception
	occurs during the restart process, and a Stop 0x0000001E blue screen results.
	
	CAUSE
	=====
	
	Some drivers for the HASP hardware key (dongle) required by QuarkXPress and
	other key-protected products are incompatible with SP4.
	
	RESOLUTION
	==========
	
	Install the latest HASP drivers before installing SP4. Any driver version later
	than 3.7 will work.
	
	If the problem is encountered after installing SP4 and rebooting, you must remove
	the existing driver. If you have a multiple boot system and one of the other
	operating systems can access the system directory for the affected boot, you can
	boot on that other operating system and remove the Haspnt.sys file from the
	System32\Drivers folder in the Windows NT system directory. If you do not have
	multiple boots that permit this, you must install Windows NT temporarily in
	another folder, log on to the temporary installation, and delete the file.
	
	Full details on this problem can be found on the HASP site, at the following
	URLs:
	
	  http://www.hasp.com/press_forum/hasp98/technotent4.html (Aladdin)
	  http://www.quark.com/tech/NT4issue.html (Quark)
	
	The third-party products discussed here are manufactured by vendors independent
	of Microsoft; we make no warranty, implied or otherwise, regarding these
	products' performance or reliability.
	
	MORE INFORMATION
	================
	
	HASP drivers 3.1 through 3.64 inclusive are affected by this error. HASP drivers
	after version 3.7 will work correctly. The blue screen does not occur in all
	configurations, but it does in most.
	
	The QuarkXPress and HASP products discussed here are manufactured by vendors
	independent of Microsoft; we make no warranty, implied or otherwise, regarding
	this product's performance or reliability.
	
	For complete information, consult Quark's Web site at
	
	  http://www.quark.com/
	
	and Aladdin's HASP Web site at
	
	  http://www.hasp.com/
	
	Additional query words: dongle SP4 hardware key Quark QuarkXPress XPress HASP Aladdin
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT400xsearch kbWinNTSsearch kbWinNTS400xsearch kbWinNTS400
	Version           : WinNT:4.0
	Hardware          : ALPHA x86
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
