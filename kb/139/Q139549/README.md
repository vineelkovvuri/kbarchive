---
layout: page
title: "Q139549: BUG: Using RUN to Shell to MS-DOS Results in ICE Error"
permalink: /kb/139/Q139549/
---

## Q139549: BUG: Using RUN to Shell to MS-DOS Results in ICE Error

{% raw %}

	Article: Q139549
	Product(s): Microsoft FoxPro
	Version(s): WINDOWS:3.0,3.0b
	Operating System(s): 
	Keyword(s): kbenv kbvfp kbvfp300bBUGkbbuglist
	Last Modified: 10-FEB-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 3.0, 3.0b 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Using the RUN command to shell to MS-DOS results in an ICE (Internal Consistency
	Error). This occurs when Visual FoxPro is running on a computer that has the
	following characteristics:
	
	- The computer uses a 16-bit operating system, such as Microsoft Windows or
	  Microsoft Windows for Workgroups.
	
	- The computer uses Win32s to provide the Win32s API to Visual FoxPro.
	
	- The computer uses Novell Netware 3.11 MS-DOS network drivers.
	
	CAUSE
	=====
	
	The precise cause of this problem has not been determined, but the problem
	appears to be related to a conflict between Win32s and the Novell 3.11
	requestor.
	
	RESOLUTION
	==========
	
	Upgrade to version 3.12 or higher of the Novell requestor or upgrade to a 32-bit
	operating system such as Windows 95 or Windows NT that does not require Win32s.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products listed at
	the beginning of this article. We are researching this problem and will post new
	information here in the Microsoft Knowledge Base as it becomes available.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbenv kbvfp kbvfp300bBUG kbbuglist
	Technology        : kbVFPsearch kbAudDeveloper kbVFP300 kbVFP300b
	Version           : WINDOWS:3.0,3.0b
	
	=============================================================================
	

{% endraw %}
