---
layout: page
title: "Q171502: FIX: Crash with Watch on UserControl When Stop is Encountered"
permalink: /kb/171/Q171502/
---

## Q171502: FIX: Crash with Watch on UserControl When Stop is Encountered

{% raw %}

	Article: Q171502
	Product(s): Microsoft Visual Basic for Windows
	Version(s): 5.0
	Operating System(s): 
	Keyword(s): kbVBp500 kbVS97sp2fix kbGrpDSVB kbvbp500sp2fix
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Learning Edition for Windows, version 5.0 
	- Microsoft Visual Basic Professional Edition for Windows, version 5.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 5.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Visual Basic may crash when a Stop action or Breakpoint is encountered in the
	ReadProperties event of a UserControl.
	
	CAUSE
	=====
	
	The ReadProperties event occurs before a UserControl is completely loaded.
	
	If a Runtime error, Stop statement, or Breakpoint is encountered during this
	time, and a Watch is set on a variable of the UserControl, Visual Basic may
	crash.
	
	RESOLUTION
	==========
	
	Install Visual Studio 97 Service Pack 2 (SP2) or do not use a Stop statement or
	Breakpoint in the ReadProperties event of a UserControl when a watch is set on a
	UserControl variable.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a bug in the Microsoft products listed at the
	beginning of this article. This bug has been fixed in Visual Studio 97 Service
	Pack 2.
	
	For more information on the Visual Studio 97 Service Pack 2, please see the
	following article in the Microsoft Knowledge Base:
	
	  Q170365 INFO: Visual Studio 97 Service Packs - What, Where, and Why
	
	For a list of the Visual Basic 5.0 bugs that were fixed in the Visual Studio 97
	Service Pack 2, please see the following article in the Microsoft Knowledge
	Base:
	
	  Q171554 INFO: Visual Basic 5.0 Fixes in Visual Studio 97 Service Pack 2
	
	MORE INFORMATION
	================
	
	This may occur if you are running in a multi-UserControl environment and set a
	watch value to the UserControl.
	
	Steps to Reproduce Behavior
	---------------------------
	
	1. Start a new Standard EXE project in Visual Basic 5.0.
	
	2. Insert a UserControl into the project by selecting "Add User Control" from
	  the Project menu. Place an instance of the UserControl on Form1.
	
	3. Paste the following code in the UserControl_Readproperties event:
	
	        Private Sub UserControl_ReadProperties(PropBag As PropertyBag)
	           Stop
	        End Sub
	
	4. Place a second instance of the UserControl on Form1.
	
	5. Add the following watches:
	
	        Form1.UserControl11
	        Form1.UserControl12
	
	6. Press the F5 key to execute the project.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbVBp500 kbVS97sp2fix kbGrpDSVB kbvbp500sp2fix 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVBA500 kbVB500
	Version           : 5.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
