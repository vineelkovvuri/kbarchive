---
layout: page
title: "Q272462: Runtime Error in MapPoint or Streets and Trips"
permalink: /kb/272/Q272462/
---

## Q272462: Runtime Error in MapPoint or Streets and Trips

{% raw %}

	Article: Q272462
	Product(s): Microsoft Automap
	Version(s): 
	Operating System(s): 
	Keyword(s): kbenv kberrmsg kbhw kbimu kbHardware
	Last Modified: 07-JUN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft MapPoint 2001 
	- Microsoft Streets and Trips 2001 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you use the Find or Route Planning feature in any of the programs listed at
	the beginning of this article, you may receive the following error message:
	
	  C++ Runtime Error...
	
	  Abnormal Program Termination.
	
	CAUSE
	=====
	
	This behavior can occur if any of the following conditions are true:
	
	- A real mode (16-bit) CD-ROM driver is installed on your computer.
	
	- Microsoft Data Access Components (MDAC) are damaged or not installed
	  properly.
	
	- The program CD-ROM is damaged or dirty.
	
	RESOLUTION
	==========
	
	To resolve this issue, use the following methods in the order in which they are
	presented.
	
	Clean the CD-ROM
	----------------
	
	Clean the CD-ROM. To do this, use a CD-ROM cleaning kit, or gently wipe the
	silver side of the CD-ROM with a soft, lint-free cotton cloth. Do not use paper
	cloth which can scratch the plastic and leave streaks. When you clean the
	CD-ROM, wipe from the center of the disc outward. Do not use a circular motion.
	
	If the issue continues to occur, clean the CD-ROM with a damp cloth or a
	commercial CD cleaning solution. Dry the CD-ROM thoroughly before you insert it
	into the CD-ROM drive.
	
	
	If the issue continues to occur, proceed to the next method.
	
	Inspect the CD-ROM
	------------------
	
	Inspect the CD-ROM for visible deformation or scratches. If the disc is damaged,
	contact Microsoft Sales at (800) 360-7561 to obtain a replacement CD-ROM. You
	can also order it online at the following Microsoft Web site:
	
	  http://parts.microsoft.com
	
	NOTE: If the CD-ROM was provided with your computer, you need to contact your
	computer manufacturer to obtain a replacement CD-ROM.
	
	For information about how to contact your computer manufacturer, click the
	appropriate article number below to view the article in the Microsoft Knowledge
	Base:
	
	  Q65416 Hardware and Software Third-Party Vendor Contact List, A-K
	
	  Q60781 Hardware and Software Third-Party Vendor Contact List, L-P
	
	  Q60782 Hardware and Software Third-Party Vendor Contact List, Q-Z
	
	If the issue continues to occur, proceed to the next method.
	
	Make Sure That You Use a Protected Mode CD-ROM Driver
	-----------------------------------------------------
	
	To make sure that you use a protected mode (32-bit) CD-ROM driver for your CD-ROM
	drive:
	
	1. Click Start, point to Settings, and then click Control Panel.
	
	2. Double-click System.
	
	3. Click the Performance tab, and then confirm that the File System entry is
	  32-bit.
	
	  If the File System entry states "Some drives are using MS-DOS compatibility",
	  you may be using real mode (16-bit) CD-ROM drivers.
	
	  Contact the manufacturer of your CD-ROM drive to obtain an updated, protected
	  mode (32-bit) CD-ROM driver for your CD-ROM drive.
	
	4. Click OK, and then close Control Panel.
	
	For information about how to contact the manufacturer of your CD-ROM drive, click
	the appropriate article number below to view the article in the Microsoft
	Knowledge Base:
	
	  Q65416 Hardware and Software Third-Party Vendor Contact List, A-K
	
	  Q60781 Hardware and Software Third-Party Vendor Contact List, L-P
	
	  Q60782 Hardware and Software Third-Party Vendor Contact List, Q-Z
	
	If the issue continues to occur, proceed to the next method.
	
	Download and Install the MDAC 2.5 Update
	----------------------------------------
	
	To download and install the MDAC 2.5 Update:
	
	1. Connect to the following Microsoft Web site:
	
	  http://www.microsoft.com/downloads
	
	2. Scroll down the page until you see the following:
	
	  "2.5 SP1 Release Microsoft Data Access Components 2.5 SP1 (2.51.5303.5) Now
	  Available"
	
	3. Click the "Download MDAC 2.5 SP1 (2.51.5303.5)" link.
	
	4. In the Keywords box, type "mdac" (without the quotation marks), and then
	  under "Show Results for": click "All Downloads".
	
	5. Click "Find It!" In the list of found download files, click the following:
	
	  "MDAC (Microsoft Data Access Components) 2.5 Update: Service Pack 1
	  (2.51.5303.5)"
	
	6. Under "Download Now", click the "MDAC_TYP.EXE - 7,857 Kb" link.
	
	7. Double-click the Mdac_typ.exe file on the Windows desktop.
	
	8. Follow the instructions on the screen to install the MDAC 2.5 update.
	
	9. When you receive the prompt to restart the computer, do so.
	
	If you encounter problems installing the MDAC 2.5 Update, restart the computer in
	Safe mode, and then repeat these steps.
	
	To restart the computer in Safe mode:
	
	1. Press and hold down the CTRL key when you see the "Starting Windows 98"
	  message (in Microsoft Windows 98) or press F8 when you see the "Starting
	  Windows 95" message (in Microsoft Windows 95) on the screen.
	
	2. Select Safe Mode from the Startup menu.
	
	
	MORE INFORMATION
	================
	
	For additional information about how to troubleshoot CD-ROM read errors, click
	the article number below to view the article in the Microsoft Knowledge Base:
	
	  Q218617 How to Troubleshoot CD-ROM Read Issues
	
	Additional query words: mp2001 map point st2001 auto-map amap
	
	======================================================================
	Keywords          : kbenv kberrmsg kbhw kbimu kbHardware 
	Technology        : kbHomeProdSearch kbExpediaSearch kbMapptSearch kbMapPoint2001
	Version           : :
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
