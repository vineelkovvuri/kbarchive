---
layout: page
title: "Q148357: FIX: Class Designer Changes the Width of a Form Class"
permalink: /kb/148/Q148357/
---

## Q148357: FIX: Class Designer Changes the Width of a Form Class

{% raw %}

	Article: Q148357
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
	
	In Visual FoxPro, Microsoft recommends that forms and classes be designed using
	the Foxels measurement instead of the Pixels measurement when an application is
	intended to be used across platforms or when the font metrics are likely to
	change (small to large, for example).
	
	However, if a Form class is created using the Class Designer with the scalemode
	set to Foxel and width set to a specific number, the width of the form may be
	reduced or enlarged depending on the font used. For example, it is reduced by
	twenty five percent (25%) after the class has been changed to Courier New from
	Arial, saved, and modified again. This is demonstrated in the following article
	in the Microsoft Knowledge Base:
	
	  Q129208 Pixel Replaces Foxel as Default Scale Value in Design Mode
	
	WORKAROUND
	==========
	
	To prevents this from happening, change the Scalemode property to Pixels or
	don't change the Fontname property from Arial.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products listed at
	the beginning of this article. This problem has been fixed in Visual FoxPro 5.0
	for Windows.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Problem
	--------------------------
	
	1. Using the Visual FoxPro class designer, create a new class based on Form.
	
	2. Set the properties of the form as follows:
	
	     FontName = "Courier New"
	     ScaleMode = "Foxels"
	     Width = 100
	
	3. Save the class in a class Library.
	
	4. Modify the class.
	
	Note that the width is now 75 instead of the initial setting of 100. Each
	subsequent save or modification results in 25% reduction in the width.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbvfp kbvfp300bBUG kbvfp500fix kbbuglist kbfixlist
	Technology        : kbVFPsearch kbAudDeveloper kbVFP300 kbVFP300b
	Version           : WINDOWS:3.0,3.0b
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
