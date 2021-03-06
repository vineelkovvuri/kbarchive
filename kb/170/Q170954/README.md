---
layout: page
title: "Q170954: WD97: E-Mail File Attachments Display as Empty Outlined Box"
permalink: /kb/170/Q170954/
---

## Q170954: WD97: E-Mail File Attachments Display as Empty Outlined Box

{% raw %}

	Article: Q170954
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbinterop kbusage kbdta kbemail word97
	Last Modified: 14-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	- Microsoft Outlook 97 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you view an e-mail message containing a file attachment, the attachment
	displays as an empty black outlined box instead of displaying the attachment
	icon and file name of the attachment.
	
	CAUSE
	=====
	
	The above behavior may occur if all of the following are true:
	
	- You are using Microsoft Word as your email editor.
	
	  -and-
	
	- You have the Word Picture Placeholders option turned on.
	
	RESOLUTION
	==========
	
	To display the attachment icon and file name, turn off the picture placeholders
	option by following these steps:
	
	Creating and sending e-mail from Microsoft Outlook or Microsoft Exchange
	------------------------------------------------------------------------
	
	1. In Microsoft Outlook or Microsoft Exchange, create or open an e-mail message.
	
	2. Click in the body of the e-mail message or press the Tab key three times to
	  move the insertion point into the body of the message.
	
	3. On the Tools menu, click Options.
	
	4. On the View Tab, click to clear (uncheck) the Picture Placeholders checkbox.
	
	5. Click OK.
	
	The attachment icon and file name should now appear normally.
	
	Sending a document as an attachment from Microsoft Word
	-------------------------------------------------------
	
	1. On the Tools menu, click Options.
	
	2. On the View Tab, click to clear (uncheck) the Picture Placeholders checkbox.
	
	3. Click OK.
	
	When you send a document as an attachment from Microsoft Word(On the File menu
	click Send To), the icon and file name should now appear normally.
	
	To send a document as an attachment from Word:
	
	1. On the Tools menu click Options.
	
	2. On the General tab click to check the "Mail as attachment" checkbox.
	
	MORE INFORMATION
	================
	
	Microsoft Outlook and Microsoft Exchange give you the option to use Word as your
	email editor.
	
	With Word as your email editor, most of the editing features available in Word
	are available when working with e-mail messages. The Picture Placeholder option
	in Word can be used to display an empty outlined box in place of each graphic in
	your document to increase the speed at which you can scroll through and display
	a document containing many graphics.
	
	REFERENCES
	==========
	
	For additional information, please see the following article(s) in the Microsoft
	Knowledge Base:
	
	  Q166344 OL97: File Attachments Will not Open When Using Wordmail
	
	
	  Q159476 WD97: How to Enable, Disable Microsoft Word as the E-Mail Editor
	
	For more information about "picture placeholders," click the Office Assistant,
	type "picture placeholders," click Search, and then click "Speed up scrolling by
	hiding graphics."
	
	NOTE: If the Assistant is hidden, click the Office Assistant button on the
	Standard toolbar. If Microsoft Help is not installed on your computer, please
	see the following article in the Microsoft Knowledge Base:
	
	  Q120802 Office: How to Add/Remove a Single Office Program or Component
	
	Additional query words: ol97 word97 square boxes frame email
	
	======================================================================
	Keywords          : kbinterop kbusage kbdta kbemail word97 
	Technology        : kbWordSearch kbOutlookSearch kbWord97 kbWord97Search kbZNotKeyword2 kbOutlook97Search kbZNotKeyword3
	Version           : WINDOWS:97
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
