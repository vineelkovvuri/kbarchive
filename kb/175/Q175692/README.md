---
layout: page
title: "Q175692: PRB: Unable to Remove Previous MSDN Installation"
permalink: /kb/175/Q175692/
---

## Q175692: PRB: Unable to Remove Previous MSDN Installation

{% raw %}

	Article: Q175692
	Product(s): Microsoft Developer Network
	Version(s): winnt:
	Operating System(s): 
	Keyword(s): kbide kbInfoViewer kbMSDN kbVC kbVS kbGrpDSTools
	Last Modified: 22-APR-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Developer Network (MSDN), versions January 97, April 97, July 97, October 97, January 98, April 98, July 98 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	This article applies only to versions of the MSDN Library between January 97 and
	July 98. These versions used the InfoViewer technology, while newer versions use
	HTML Help. When you uninstall versions of Microsoft Developer Network (MSDN)
	Library from January 97 through July 98, the following error occurs:
	
	  An error occurred while trying to remove Microsoft Developer Network.
	  Uninstallation has been canceled.
	
	CAUSE
	=====
	
	This might be caused by a missing or corrupted MSDN Setup.exe. This file can be
	found in <DevStudio Path>\MSDN\Setup\Setup.exe.
	
	RESOLUTION
	==========
	
	To install the new version of MSDN, you must follow these steps:
	
	1. Reinstall the older version of MSDN. This fixes/replaces Setup.exe.
	
	2. On the Start Menu, point to Settings and click Control Panel.
	
	3. Double-click the Add/Remove Programs icon.
	
	4. In the Add/Remove Programs dialog box, select the older version of MSDN.
	
	5. Click the Add/Remove button.
	
	6. Click Remove All.
	
	Now that the existing version of MSDN has successfully been removed, you can
	install a new version of MSDN.
	
	MORE INFORMATION
	================
	
	WARNING: Using Registry Editor incorrectly can cause serious, system-wide
	problems that may require you to reinstall Windows to correct them. Microsoft
	cannot guarantee that any problems resulting from the use of Registry Editor can
	be solved. Use this tool at your own risk.
	
	If you are unable to reinstall the existing version of the MSDN, you can manually
	delete a large part of MSDN on the hard drive and in the registry. It is
	important to reinstall and immediately uninstall, because the MSDN's uninstall
	will clean out all the files and registry entries for each version. This will
	prevent other MSDN problems in the future.
	
	How To Remove Most of the MSDN Manually Before Reinstall
	--------------------------------------------------------
	
	1. On the taskbar, select Start and click Run.
	
	2. Type Regedit and press return.
	
	3. The Windows registry editor should appear.
	
	4. Expand the branches until you reach:
	
	     [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Infoviewer\5.0]
	
	5. Delete the version 5.0 subkey under the Infoviewer branch.
	
	6. From the Registry menu, click Exit to close RegEdit.
	
	7. Use the Windows Explorer to find "<DevStudio Path>\MSDN".
	
	8. In the MSDN directory delete the Setup and Bin directories.
	
	9. Reinstall and uninstall the old version of MSDN to clean out all other
	  registry entries and files.
	
	At this point, you should be able to install a newer version of MSDN
	successfully.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbide kbInfoViewer kbMSDN kbVC kbVS kbGrpDSTools 
	Technology        : kbMSDNSearch kbZNotKeyword2 kbMSDNJuly98 kbMSDNOct97 kbMSDNJan98 kbMSDNApril98 kbMSDNApril97
	Version           : winnt:
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
