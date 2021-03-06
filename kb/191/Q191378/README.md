---
layout: page
title: "Q191378: WD97: Print: Odd Pages and Even Pages Have Opposite Effect"
permalink: /kb/191/Q191378/
---

## Q191378: WD97: Print: Odd Pages and Even Pages Have Opposite Effect

{% raw %}

	Article: Q191378
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbdta word97
	Last Modified: 14-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	When you select Odd Pages or Even Pages in the Print dialog box, you may get the
	opposite result when you print the document.
	
	CAUSE
	=====
	
	This opposite result will occur if the document begins with an even page number
	(such as 2, 4, or 6). This problem only occurs with documents starting with even
	page numbers; it does not occur if your document starts with an odd page
	number.
	
	This behavior occurs because Word does not use the page number to determine odd
	or even pages. Instead, Word prints even or odd pages based on the physical
	order of the pages; this means the first page is odd, the second page is even,
	the third page is odd, the fourth page is even, and so forth.
	
	WORKAROUND
	==========
	
	Use one of the following methods when you print your document.
	
	Method 1: Use the Other Option
	------------------------------
	
	If a document begins with an even page number and you want to print using the Odd
	or Even Pages option, choose the opposite option in the Print dialog box. For
	example, if you want to print even pages, select the Odd Pages option.
	
	Method 2: Insert a Page Break at the Beginning of the Document
	--------------------------------------------------------------
	
	To insert a page break at the beginning of the document, follow these steps:
	
	1. On the Insert menu, click Break.
	
	2. In the Break box, Select Page Break, and click OK.
	
	The Odd Pages or Even Pages option will work as expected.
	
	NOTE: When you print your document, a blank page prints at the beginning of the
	document. This blank page is a result of the page break that you inserted and
	can be discarded.
	
	Additional query words: incorrect wrong inconsistent
	
	======================================================================
	Keywords          : kbdta word97 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
