---
layout: page
title: "Q141806: FIX: Errors Previewing Customer Listing Report in Tastraders"
permalink: /kb/141/Q141806/
---

## Q141806: FIX: Errors Previewing Customer Listing Report in Tastraders

{% raw %}

	Article: Q141806
	Product(s): Microsoft FoxPro
	Version(s): WINDOWS:3.0,3.0b
	Operating System(s): 
	Keyword(s): kbvfp kbvfp300bBUG kbvfp500fixkbbuglist kbfixlist
	Last Modified: 24-MAR-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 3.0, 3.0b 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When previewing the Customer listing report in the Tastraders application, you
	may notice that the date or page number has been truncated.
	
	CAUSE
	=====
	
	This is typically caused by the printer driver that is being used, although the
	date output may also be affected by the CENTURY setting in Visual FoxPro. If
	Century is turned on, you may only see 19 and not the complete date.
	
	WORKAROUND
	==========
	
	You may need to move some of the report objects away from the outer edges of the
	report or consider using a somewhat smaller font.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products listed at
	the beginning of this article. This problem has been fixed in Visual FoxPro 5.0
	for Windows.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Problem
	--------------------------
	
	The problem is not specific to any particular driver, so the following steps may
	not produce the problem.
	
	1. Start TasTrade, and log in.
	
	2. On the File menu, click Print Reports.
	
	3. Select Listings for output type.
	
	4. Select Customer Listing.
	
	5. Preview the report.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbvfp kbvfp300bBUG kbvfp500fix kbbuglist kbfixlist
	Technology        : kbVFPsearch kbAudDeveloper kbVFP300 kbVFP300b
	Version           : WINDOWS:3.0,3.0b
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
