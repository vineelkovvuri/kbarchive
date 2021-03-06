---
layout: page
title: "Q266255: XCLN: Default .pst File Creation Path Needs to Be Configurable"
permalink: /kb/266/Q266255/
---

## Q266255: XCLN: Default .pst File Creation Path Needs to Be Configurable

{% raw %}

	Article: Q266255
	Product(s): Microsoft Exchange
	Version(s): 
	Operating System(s): 
	Keyword(s): 
	Last Modified: 06-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Outlook 2000 
	- Microsoft Exchange Server, version 5.5 
	-------------------------------------------------------------------------------
	
	
	IMPORTANT: This article contains information about modifying the registry. Before you 
	modify the registry, make sure to back it up and make sure that you understand how to restore 
	the registry if a problem occurs. For information about how to back up, restore, and edit the 
	registry, click the following article number to view the article in the Microsoft Knowledge Base:
	
	  Q256986 Description of the Microsoft Windows Registry
	
	SYMPTOMS
	========
	
	When you add personal folder files to your e-mail profile, the default path is
	the following:
	
	  Application Data\Microsoft\Outlook
	
	You can change this path manually, but the path always defaults to the preceding
	path. You cannot change this path default to another path.
	
	RESOLUTION
	==========
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem that is described in this article. Only apply it to systems
	that are experiencing this specific problem. This fix may receive additional
	testing. Therefore, if you are not severely affected by this problem, Microsoft
	recommends that you wait for the next Microsoft Office 2000 service release that
	contains this fix.
	
	To resolve this problem immediately, contact Microsoft Product Support Services
	to obtain the fix. For a complete list of Microsoft Product Support Services
	phone numbers and information about support costs, visit the following Microsoft
	Web site:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	NOTE: In special cases, charges that are ordinarily incurred for support calls
	may be canceled if a Microsoft Support Professional determines that a specific
	update will resolve your problem. The usual support costs will apply to
	additional support questions and issues that do not qualify for the specific
	update in question.
	
	The English version of this fix should have the following file attributes or
	later:
	
	Component: Outlook
	
	Depending on whether or not you have the Outlook Security Patch on installed on
	you computer, you will need different fixes; however both sets of fixes require
	Outlook 2000 Service Release 1 (SR1) to be installed.
	
	The Security Patch version of this fix is 2115.
	The non-Security Patch version of this fix is 2439.
	
	The fixes include two Client.msp files and two Admin.msp files. One .msp file is
	the Outlook portion of the fix and the other is the MAPI portion of the fix. You
	must install both .msp files.
	
	Files included with the 2115 fix:
	
	  OQFE7760_Admin.msp
	  OQFE7760_Client.msp
	  OQFE7772_Admin.msp
	  OQFE7772_Client.msp
	
	Files included with the 2439 fix:
	
	  OQFE7772_Admin.msp
	  OQFE7772_Client.msp
	  OQFE7819_Admin.msp
	  OQFE7819_Client.msp
	
	+------------------------------+
	| File name   | Version        | 
	+------------------------------+
	| Mspst32.dll | 5.05.3138.0000 | 
	+------------------------------+
	| Outllib.dll | 9.00.00.4326   | 
	+------------------------------+
	
	After the correct files are in place, you must add the ForcePSTPath string value
	to the following registry key:
	
	WARNING: If you use Registry Editor incorrectly, you may cause serious problems
	that may require you to reinstall your operating system. Microsoft cannot
	guarantee that you can solve problems that result from using Registry Editor
	incorrectly. Use Registry Editor at your own risk.
	
	  HKEY_LOCAL_MACHINE\Software\Microsoft\Office\9.0\Outlook
	
	  Value name: ForcePSTPath
	  Value data (SZ): <drive>:\<path>\
	
	The following example changes the default path to the C:\Allpsts folder:
	
	Value name: ForcePSTPath
	Value data (SZ): c:\allpsts
	
	1. Click Start, point to Run, and then type "regedit" (without the quotation
	  marks) to start Registry Editor.
	
	2. Locate the following registry key:
	
	  HKEY_LOCAL_MACHINE\Software\Microsoft\Office\9.0\Outlook\
	
	3. On the Edit menu, point to New, click String Value, and then add the
	  following registry value:
	
	  Name: ForcePSTPath
	
	4. Locate and select the following key in the registry:
	
	  HKEY_LOCAL_MACHINE\Software\Microsoft\Office\9.0\Outlook\ForcePSTPath
	
	5. In the right-pane, double-click the ForcePSTPath icon.
	
	6. In the Value data box, type the drive letter and folder path in which you
	  want the Personal Folder files to be created in. In this example, c:\allpsts.
	  Click OK.
	
	7. Quit Registry Editor.
	
	
	
	STATUS
	======
	
	Microsoft has confirmed that this is a problem in Microsoft Outlook 2000.
	
	Additional query words: OL2000
	
	======================================================================
	Keywords          :  
	Technology        : kbOutlookSearch kbExchangeSearch kbExchange550 kbZNotKeyword2 kbOutlook2000Search kbZNotKeyword3
	Version           : :
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
