---
layout: page
title: "Q181361: WD97: Text/Table Disappears Following Check Box Form Field"
permalink: /kb/181/Q181361/
---

## Q181361: WD97: Text/Table Disappears Following Check Box Form Field

{% raw %}

	Article: Q181361
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbfield word97
	Last Modified: 14-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you embed a file or selected text that contains a check box form field, one
	or both of the following cases may occur.
	
	Case 1
	------
	
	Text or other parts of the file immediately following the check box form field
	will be missing.
	
	Case 2
	------
	
	If the check box form field is contained in a table, text and table borders
	following the check box will be missing.
	
	WORKAROUND
	==========
	
	Do not insert the file or selected text containing the check box form field as
	an embedded object. Use one of the following methods instead.
	
	Method 1: Insert the File
	-------------------------
	
	1. In your new document, click File on the Insert menu.
	
	2. Select the file that contains the check box form field, and then click OK.
	
	  NOTE: Click the Link To File check box in the Insert File dialog box, if you
	  want to link to the file instead of embedding the file.
	
	Method 2: Copy and Paste the File as a Word Hyperlink
	-----------------------------------------------------
	
	1. In the document containing the check box form field, select the text of the
	  document, and then on the Edit menu, click Copy.
	
	2. In your new document, click Paste special on the Edit menu.
	
	3. In the Paste Special dialog box, click to select the Paste Link button. In
	  the "As" box, click Word Hyperlink, and then click OK.
	
	  NOTE: Do not use Paste Special to paste the text as an object or picture
	  because then the same problem will occur.
	
	Word will insert a hyperlink into your new document that will be blue and
	underlined by default. To change the appearance of the hyperlink, follow these
	steps:
	
	1. Select the hyperlink.
	
	2. On the Format menu, click Font.
	
	3. In the Underline box, select None.
	
	4. In the Color box, select Auto.
	
	5. Click OK.
	
	NOTE: When you click the hyperlink, Word will automatically open your linked
	document.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products listed at
	the beginning of this article.
	This problem was corrected in Word 2000.
	
	REFERENCES
	==========
	
	For more information about embedding a document, click Contents And Index on the
	Help menu, click the Index tab in Help Topics: Microsoft Word, type the
	following text
	
	  embedded objects, creating
	
	and then double-click the selected text to go to the "Create a linked object or
	embedded object from an existing file" topic. If you are unable to find the
	information you need, ask the Office Assistant.
	
	Additional query words: gone deleted masked
	
	======================================================================
	Keywords          : kbfield word97 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	Issue type        : kbbug
	Solution Type     : kbpending
	
	=============================================================================
	

{% endraw %}
