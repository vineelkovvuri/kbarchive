---
layout: page
title: "Q170267: WD97: WordBasic MacroCopy Command Fails"
permalink: /kb/170/Q170267/
---

## Q170267: WD97: WordBasic MacroCopy Command Fails

{% raw %}

	Article: Q170267
	Product(s): Word 97 for Windows
	Version(s): Service Release 1 (SR-1)
	Operating System(s): 
	Keyword(s): kbmacro kbusage kbwordvba winword word97
	Last Modified: 26-OCT-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows, version Service Release 1 (SR-1) 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you attempt to use a WordBasic.MacroCopy command to copy a macro from any
	location other than a local template to any location other than a global
	template, the copy may fail.
	
	The table that follows details how the WordBasic.MacroCopy, WordBasic.Organizer,
	and Application.OrganizerCopy commands perform in Microsoft Word 97 SR-1.
	
	NOTE: "Global Temp" indicates any template loaded globally (that is, it is loaded
	by clicking Templates And Add-Ins on the Tools menu).
	
	An error will be generated when you try to perform any of the illegal copies. The
	error message will change depending on the command used and the target.
	
	Using WordBasic.MacroCopy
	-------------------------
	
	  Source       Target        Valid  Err  Error Message
	  ----------------------------------------------------
	  
	  Document     Document      Yes
	  Document     Template      Yes
	  Document     Normal        Yes
	  Document     Global Temp   No*    24   Bad Parameter
	  Template     Document      Yes
	  Template     Template      Yes
	  Template     Normal        Yes
	  Template     Global Temp   No*    24   Bad Parameter
	  Normal       Document      No     24   Bad Parameter
	  Normal       Template      No     24   Bad Parameter
	  Normal       Normal        No     24   Bad Parameter
	  Normal       Global Temp   No     24   Bad Parameter
	  Global Temp  Document      No     24   Bad Parameter
	  Global Temp  Template      No     24   Bad Parameter
	  Global Temp  Normal        No     24   Bad Parameter
	  Global Temp  Global Temp   No     24   Bad Parameter
	
	Using WordBasic.Organizer
	-------------------------
	
	  Source       Target        Valid  Err  Error Message
	  ------------------------------------------------------------------------
	  
	  Document     Document      Yes
	  Document     Template      Yes
	  Document     Normal        Yes
	  Document     Global Temp   No*    1844 The project item cannot be copied
	  Template     Document      Yes
	  Template     Template      Yes
	  Template     Normal        Yes
	  Template     Global Temp   No*    1844 The project item cannot be copied
	  Normal       Document      No     102  Command failed
	  Normal       Template      No     102  Command failed
	  Normal       Normal        No     102  Command failed
	  Normal       Global Temp   No     102  Command failed
	  Global Temp  Document      No     102  Command failed
	  Global Temp  Template      No     102  Command failed
	  Global Temp  Normal        No     102  Command failed
	  Global Temp  Global Temp   No     1844 The project item cannot be copied
	
	Using Application.OrganizerCopy
	-------------------------------
	
	  Source       Target        Valid  Err  Error Message
	  ------------------------------------------------------------------------
	  
	  Document     Document      Yes
	  Document     Template      Yes
	  Document     Normal        Yes
	  Document     Global Temp   No*    5940 The project item cannot be copied
	  Template     Document      Yes
	  Template     Template      Yes
	  Template     Normal        Yes
	  Template     Global Temp   No*    5940 The project item cannot be copied
	  Normal       Document      No     4198 Command failed
	  Normal       Template      No     4198 Command failed
	  Normal       Normal        No     4198 Command failed
	  Normal       Global Temp   No     4198 Command failed
	  Global Temp  Document      No     4198 Command failed
	  Global Temp  Template      No     4198 Command failed
	  Global Temp  Normal        No     4198 Command failed
	  Global Temp  Global Temp   No     5940 The project item cannot be copied
	
	* Copying from a document or template to a global template will work if the
	global tempalte is open in Word for editing.
	
	CAUSE
	=====
	
	This functionality is by design in Microsoft Word 97 SR-1, in an effort to
	reduce the spread of macro viruses. This behavior is different from Microsoft
	Word 97. In Microsoft Word 97, the command will be executed as expected.
	
	WORKAROUND
	==========
	
	Instead of using the WordBasic object to copy macros from one location to
	another, use the Microsoft Word 97 object model.
	
	For more information about equivalent commands in the Microsoft Word 97 object
	model, click the Office Assistant, type "What is WordBasic.MacroCopy?," click
	Search, and then click to view "Visual Basic Equivalents for WordBasic
	Commands."
	
	NOTE: You must be in the Visual Basic Editor before you click the Office
	Assistant for help.
	
	NOTE: If the Assistant is hidden, click the Office Assistant button on the
	Standard toolbar. If Word Help is not installed on your computer, please see the
	following article in the Microsoft Knowledge Base:
	
	  Q120802 Office: How to Add/Remove a Single Office Program or Component
	
	REFERENCES
	==========
	
	For more information about macro viruses, please see the following articles in
	the Microsoft Knowledge Base:
	
	  Q134727 WD: What to Do If You Have a Macro Virus
	
	  Q163932 WD: Frequently Asked Questions About Word Macro Viruses
	
	
	For more information about macro viruses, click the Office Assistant, type "macro
	virus," click Search, and then click "Check documents for macros that might
	contain viruses."
	
	Additional query words: sr1 release1 8.0
	
	======================================================================
	Keywords          : kbmacro kbusage kbwordvba winword word97 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2 kbWord97SR1
	Version           : :Service Release 1 (SR-1)
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
