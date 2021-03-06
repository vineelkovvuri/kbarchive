---
layout: page
title: "Q173254: VB5 Step By Step: Page 24, Step 6 Causes Illegal Operation"
permalink: /kb/173/Q173254/
---

## Q173254: VB5 Step By Step: Page 24, Step 6 Causes Illegal Operation

{% raw %}

	Article: Q173254
	Product(s): Microsoft Press
	Version(s): 
	Operating System(s): 
	Keyword(s): 
	Last Modified: 07-JAN-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- MSPRESS Microsoft Visual Basic 5.0 Step by Step ISBN 1-57231-435-4 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Microsoft Visual Basic 5.0 Step by Step, page 24 step 6, asks you to change the
	font properties for three labels. When you perform this step, you may see the
	following error message:
	
	  This program has performed an illegal operation and will be shut down. If the
	  problem persists, contact the program vendor. VB5 caused an invalid page
	  fault in module VB5.EXE.
	
	The Visual Basic development environment will then close.
	
	CAUSE
	=====
	
	This error is the result of a known bug in Microsoft Visual Basic 5.0. The
	following text is taken from the Readme.hlp file included with the Visual Basic
	5.0 program:
	
	  If the Properties window is floating, and two or more controls are selected,
	  and you change the Font property of the controls using the floating
	  Properties window, a program fault will occur in Visual Basic.
	
	WORKAROUND
	==========
	
	In step 6, rather than changing the font property for all three labels
	simultaneously, change the font properties as shown for each label in
	succession.
	
	  -or-
	
	Make sure the properties window is docked before beginnning the steps at the
	bottom of page 23.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a bug in Microsoft Visual Basic 5.0 for
	Windows. This bug was corrected in Visual Studio 97 Service Pack 2
	
	For more information on the Visual Studio 97 Service Pack 2, please see the
	following article in the Microsoft Knowledge Base:
	
	  Q170365 INFO: Visual Studio 97 Service Packs - What, Where, and Why
	
	Additional query words: mspress ms_press press bookbug vbwin 5.0 1-57231- 435-4
	
	======================================================================
	Keywords          :  
	Technology        : kbMSPressSearch
	Version           : :
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
