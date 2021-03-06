---
layout: page
title: "Q258551: BUG: Incorrect Error Message When You Install VSS 5.0 Y2K"
permalink: /kb/258/Q258551/
---

## Q258551: BUG: Incorrect Error Message When You Install VSS 5.0 Y2K

{% raw %}

	Article: Q258551
	Product(s): Microsoft SourceSafe
	Version(s): 5.0
	Operating System(s): 
	Keyword(s): kbsetup kbSSafe500bug kbDSupport kbGrpDSSSafe
	Last Modified: 02-OCT-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual SourceSafe for Windows, version 5.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you upgrade Visual SourceSafe 5.0 to apply the year 2000 (Y2K) update, the
	following error message can occur:
	
	  This update can only be applied to Visual SourceSafe 5.0 Service Pack 3
	  installations. Please update your Visual SourceSafe 5.0 installation with
	  Service Pack 3 and run this update again. Exiting setup.
	
	CAUSE
	=====
	
	This error occurs because of one of the following reasons:
	
	- You attempt to run the Vssy2k.exe file with an Visual SourceSafe 5.0
	  directory that has the year 2000 (Y2K) update already installed.
	
	  -or-
	
	- You attempt to run the Vssy2k.exe file with a network client that was
	  installed from a Visual SourceSafe server that has the year 2000 (Y2K) update
	  already installed.
	
	This behavior is by design.
	
	STATUS
	======
	
	Microsoft has confirmed that this is a bug in the Microsoft products that are
	listed at the beginning of this article.
	
	MORE INFORMATION
	================
	
	If you install Visual SourceSafe 5.0 Service Pack 3 first, and then apply the
	hotfix, the error message displays incorrectly because you already have the
	version that the Vssy2k.exe file is trying to install, and it does not need to
	update the files.
	
	REFERENCES
	==========
	
	For more information about the Visual SourceSafe 5.0 Year 2000 Update, click the
	link below:
	
	  http://msdn.microsoft.com/downloads/default.asp?url=/downloads/sample.asp?url=/MSDN-FILES/027/000/243/msdncompositedoc.xml
	
	Additional query words:
	
	======================================================================
	Keywords          : kbsetup kbSSafe500bug kbDSupport kbGrpDSSSafe 
	Technology        : kbSSafeSearch kbAudDeveloper kbSSafe500
	Version           : :5.0
	Issue type        : kbbug
	Solution Type     : kbnofix
	
	=============================================================================
	

{% endraw %}
