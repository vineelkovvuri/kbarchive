---
layout: page
title: "Q51503: Requested Contents for Windows Problem Reports"
permalink: /kb/051/Q51503/
---

## Q51503: Requested Contents for Windows Problem Reports

{% raw %}

	Article: Q51503
	Product(s): Microsoft Windows Software Development Kit
	Version(s): WINDOWS:3.0,3.1
	Operating System(s): 
	Keyword(s): kb16bitonly
	Last Modified: 06-NOV-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows Software Development Kit (SDK) versions 3.0, 3.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article describes Microsoft's preferred format for submitting problem
	reports on Windows. Using this format will help us to understand the precise
	context of your problem report, enabling us to provide better answers to you and
	more helpful problem reports to our development staff.
	
	MORE INFORMATION
	================
	
	Your problem report should be structured as follows:
	
	  SEVERITY:
	  ENVIRONMENT:
	  DESCRIPTION:
	  CONFIGURATION:
	     Hardware:
	     Drivers:
	     Software:
	  DEBUG INFORMATION:
	
	Each of these sections is described below:
	
	Severity
	--------
	
	1, 2, 3, or 4. Use the following guidelines for severity:
	
	1 Critical -- Software does not work at all (crashes) or causes loss/corruption
	of data. Any situation where the system hangs or requires a cold or warm boot.
	
	2 Major -- A feature/function does not operate as designed. Any command or
	function that produces incorrect results or renders a portion of the product
	unusable.
	
	3 Minor -- Problems are generally minor in nature and do not prevent program from
	running (spelling errors, screen display errors, and so forth), or the results
	are misleading and/or difficult for the user to understand.
	
	4 Enhancement -- Problem is a design or feature fault that can be addressed in a
	future release.
	
	Environment
	-----------
	
	WINDOWS REAL or 286 PROTECT or 386 PROTECT release Version x.xx
	
	(Include debug info line from the bottom right of screen, if applicable)
	
	Description
	-----------
	
	Below is a description of the "ideal" problem report. The best problem reports
	are clear, complete, and concise. These are some points that will make it easier
	to track problem reports and enter them in our problem database.
	
	The report should state the steps necessary to reproduce the problem, the
	results, and (if available) a summary of the debug output. Try to include enough
	information that we can reproduce the problem here, but also try to keep the
	reports concise.
	
	The configuration should be at the end of the problem report so that people
	reading the report can get the gist of the problem without having to wade
	through information that may not be relevant (but the information is there in
	case it is relevant).
	
	Configuration
	-------------
	
	  Hardware: CPU/Memory/Monitor/keyboard/printer/modem/etc.
	  Drivers: Installed device drivers
	  Software: TSRs/Network drivers/etc.
	
	Debug Information
	-----------------
	
	The following is a sample of debug output that can be helpful in locating a
	problem:
	
	GENERAL PROTECTION VIOLATION
	CS=0EED SS=0F35 DS=0F35 ES=OOOO FS=0000 GS=0000
	
	  -- NV UP EI PL NZ NA PE NC
	
	0EED:00000387  MOV     AL,BYTE PTR     AL,BYTE PTR [BX]
	
	  DS:23D0=INV:0003
	
	ln
	No symbols found
	
	.dg cs
	004D: 0063p CODE NOTEPAD  (0EEE) 1065,103D
	103D: 01FFp CODE USER     (05BE) 104D,102D
	1165: 0061p CODE GDI      (03AE) 101D,100D
	115D: 001Bp FREE  009D,0075
	07B5: 000Bp CODE KEYBOARD (018E) 035D,0FE5
	
	Additional query words: 3.00 3.10
	
	======================================================================
	Keywords          : kb16bitonly 
	Technology        : kbAudDeveloper kbWin3xSearch kbSDKSearch kbWinSDKSearch kbWinSDK300 kbWinSDK310
	Version           : WINDOWS:3.0,3.1
	
	=============================================================================
	

{% endraw %}
