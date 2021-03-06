---
layout: page
title: "Q142178: How to Use Maple.adm with System Policy Editor"
permalink: /kb/142/Q142178/
---

## Q142178: How to Use Maple.adm with System Policy Editor

{% raw %}

	Article: Q142178
	Product(s): Microsoft Windows 95.x Retail Product
	Version(s): 95
	Operating System(s): 
	Keyword(s): kbnetwork kbtool win95
	Last Modified: 17-DEC-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows 95 
	-------------------------------------------------------------------------------
	
	This article contains information about using Windows 95 with a
	configuration that has not been tested and is not supported by Microsoft.
	
	If the steps described in this article do not function properly, use
	a supported configuration.
	
	SUMMARY
	=======
	
	This article describes how to merge the Microsoft Service for NetWare Directory
	Services policy file (Maple.adm) with the Admin.adm policy file included with
	Windows 95 to create a policy file that incorporates all policies from both
	files.
	
	For information about how to obtain the Microsoft Service for NetWare Directory
	Services, please see the following article in the Microsoft Knowledge Base:
	
	  Q138709 Microsoft Service for NetWare Directory Services Available
	
	MORE INFORMATION
	================
	
	The Microsoft Service for NetWare Directory Services (MSNDS) includes a file
	named Maple.adm that contains MSNDS-specific policies. This file is used with
	System Policy Editor as a template to create policy files.
	
	You can change the template in System Policy Editor by clicking Template on the
	Options menu, and then selecting the Maple.adm file.
	
	Windows 95 includes a file named Admin.adm that is used for most policies. It is
	located in the Windows\Inf folder.
	
	To create a policy file that incorporates both templates, follow these steps:
	
	1. Use any text editor (such as Notepad) to open the Admin.adm file in the
	  Windows\Inf folder.
	
	2. Run a second instance of the text editor and open the Maple.adm file in the
	  folder containing MSNDS.
	
	3. Copy the text in the Maple.adm file beginning with
	
	  CATEGORY !!NWClient4
	
	  and ending with:
	
	  END CATEGORY; Microsoft NetWare-Compatible Network
	
	  Paste the text into the Admin.adm file before the following section:
	
	  CATEGORY !!AccessControl
	
	  NOTE: When you copy the text in the Maple.adm file, make sure to include the
	  CATEGORY and END CATEGORY lines in the text you are copying.
	
	4. Copy the text in the Maple.adm file in the [Strings] section. Paste the text
	  into the bottom of the [Strings] section in the Admin.adm file.
	
	5. Save the Admin.adm file as a file named Merged.adm.
	
	6. In System Policy Editor, click Template on the Options menu, and select the
	  Merged.adm file. Note that you must close any open policy file before
	  changing the template.
	
	NOTE: System Policy Editor is not included in the floppy disk version of Windows
	95. You can download Policy.exe, a self-extracting executable file containing
	Poledit.exe, from online services. Please see the following article in the
	Microsoft Knowledge Base for information about downloading Policy.exe:
	
	  Q135315 CD-ROM Extras for Microsoft Windows 95 Upgrade
	
	======================================================================
	Keywords          : kbnetwork kbtool win95 
	Technology        : kbWin95search kbZNotKeyword3
	Version           : 95
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
