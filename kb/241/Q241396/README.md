---
layout: page
title: "Q241396: FileTool.exe Replaces the Open and Add-to-Project Features in VC"
permalink: /kb/241/Q241396/
---

## Q241396: FileTool.exe Replaces the Open and Add-to-Project Features in VC

{% raw %}

	Article: Q241396
	Product(s): Microsoft C Compiler
	Version(s): 5.0,6.0
	Operating System(s): 
	Keyword(s): kbfile kbSample kbVC500 kbVC600
	Last Modified: 02-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual C++, 32-bit Enterprise Edition, versions 5.0, 6.0 
	- Microsoft Visual C++, 32-bit Professional Edition, versions 5.0, 6.0 
	- Microsoft Visual C++, 32-bit Learning Edition, version 6.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Launching the Open File dialog box in Visual C++ using the keyboard shortcut key
	or from the File menu results in the following error:
	
	  Access Violation (0xC0000005) in DEVSHL.DLL at 0x5003eaed.
	  DevShl.Dll referenced memory at 0x0000000. The memory could not be read.
	
	The same error occurs when you select Add to Project from the Project menu and
	click Files.
	
	FileTool.exe is a sample that replaces the Open and Add to Project menu items in
	Visual C++ using the Developer Studio Object Model.
	
	The Developer Studio Object Model contains methods that both open files and add
	files to a project. The BuildProject object contains an AddFile method that adds
	files to a project. The Documents object contains an Open method that can open
	files into Developer Studio. These can be used in either a macro or Add-In.
	
	MORE INFORMATION
	================
	
	The following file is available for download from the Microsoft Download
	Center:
	
	  FileTool.exe
	  (http://download.microsoft.com/download/vc60ent/s1/6.0/w9xnt4/en-us/FileTool.exe)
	
	The self-extracting FileTool.exe file contains the following files:
	
	+-----------------------+
	| Commands.cpp    | 5KB | 
	+-----------------------+
	| Commands.h      | 1KB | 
	+-----------------------+
	| DSAddIn.cpp     | 5KB | 
	+-----------------------+
	| DSAddIn.h       | 2KB | 
	+-----------------------+
	| FileTool.cpp    | 5K  | 
	+-----------------------+
	| FileTool.def    | 1KB | 
	+-----------------------+
	| FileTool.dsp    | 5KB | 
	+-----------------------+
	| FileTool.dsw    | 1KB | 
	+-----------------------+
	| FileTool.h      | 1KB | 
	+-----------------------+
	| FileTool.odl    | 2KB | 
	+-----------------------+
	| FileTool.rc     | 5KB | 
	+-----------------------+
	| FileTool_i.c    | 2KB | 
	+-----------------------+
	| FileToolTypes.h | 7KB | 
	+-----------------------+
	| Resource.h      | 1KB | 
	+-----------------------+
	| StdAfx.cpp      | 1KB | 
	+-----------------------+
	| StdAfx.h        | 3KB | 
	+-----------------------+
	| FileTool.rc2    | 1KB | 
	+-----------------------+
	| TBarLrge.bmp    | 2KB | 
	+-----------------------+
	| TBarMedm.bmp    | 1KB | 
	+-----------------------+
	
	For additional information about how to download Microsoft Support files, click
	the article number below to view the article in the Microsoft Knowledge Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	Microsoft used the most current virus detection software available on the date of
	posting to scan this file for viruses. After it is posted, the file is housed on
	secure servers that prevent any unauthorized changes to the file.
	
	Installing the Add-In
	---------------------
	
	1. Run FileTool.Exe to extract the Visual C++ 6.0 project.
	
	2. Build the project in Visual C++ in Release or Debug configuration.
	
	3. In Visual C++, click Customize from the Tools menu.
	
	4. In the Customize dialog box, click the Add-Ins and Macro Files tab.
	
	5. Click the Browse button and locate the FileTool.dll file that was built in
	  step 2.
	
	6. Click OK to save the settings.
	
	A toolbar for the two commands appears.
	
	NOTE: Only the Open command works in Visual C++ 5.0. The AddFile method was added
	with the Visual Studio 6.0 release.
	
	Removing Shortcut Keys
	----------------------
	
	After you load the add-in, you can remove the shortcut keys for the menu items
	that stop Visual C++ and assign them to the two add-in commands by following the
	steps below:
	
	1. From the Visual C++ Tools menu, click Customize.
	
	2. In the Customize dialog box, click the Keyboard tab.
	
	3. From the Category box select File.
	
	4. In the Commands window, select FileOpen.
	
	5. In the Current keys window, select the CTRL+O entry and then click Remove.
	
	6. From the Category box select Project.
	
	7. In the Commands window, select InsertFilesIntoProject. If there is a shortcut
	  associated with it, follow step 5 to remove it. By default there is no
	  shortcut key for this item.
	
	8. From the Category box select Add-Ins.
	
	9. The two add-in commands AddFileToProject and OpenFile appear in the Commands
	  window.
	
	10. Select OpenFile then put the cursor in the Press New Shortcut Key box, press
	  the shortcut key or key combination that you want, and click Assign.
	
	11. Repeat the above step for the other command. The assigned shortcut keys for
	  the two commands appear in the Current Keys window.
	
	You may also wish to remove the menu commands and insert the AddIn commands in
	their place. To insert the new AddIn commands in the MenuBar, use the following
	steps:
	
	1. From the Visual C++ Tools menu, click Customize.
	
	2. Click the File menu and then drag the Open command off of the File popup and
	  release it.
	
	3. Click the Project menu, click Add To Project and then drag the Files command
	  off of the popup and release it.
	
	4. In the Customize dialog box, select the Commands tab.
	
	5. Select Add-ins from the Category list box.
	
	6. Drag the OpenFile command to the File menu and drop it in the space vacated
	  by the Open command.
	
	7. Drag the AddFileToProject command to the Add To Project item on the Project
	  menu and drop it in the space vacated by the Files command.
	
	When the menus have been modified as above, it is not necessary to have the AddIn
	toolbar visible.
	
	REFERENCES
	==========
	
	See the following topics in the MSDN Library
	(http://msdn.microsoft.com/library/default.htm) for Visual C++ 6.0 for
	documentation on Visual C++ Automation and associating shortcut keys in the
	Visual C++ IDE:
	
	  MSDN Library; Visual Studio Documentation; Visual C++ Documentation; Using
	  Visual C++; Visual C++ User's Guide; Automating Tasks in Visual C++
	
	  MSDN Library; Visual Studio Documentation; Visual C++ Documentation; Using
	  Visual C++; Visual C++ User's Guide; The Visual C++ Environment; Customizing
	  Visual C++; How Do I... Topics: Customizing Visual C++; Customizing Keyboard
	  Shortcuts
	
	  MSDN Library; Visual Studio Documentation; Visual C++ Documentation; Using
	  Visual C++; Visual C++ User's Guide; The Visual C++ Environment; Customizing
	  Visual C++; How Do I... Topics: Customizing Visual C++; Customizing Toolbars
	  and Menus
	
	Additional query words:
	
	======================================================================
	Keywords          : kbfile kbSample kbVC500 kbVC600 
	Technology        : kbVCsearch kbAudDeveloper kbVC500 kbVC600 kbVC32bitSearch kbVC500Search
	Version           : :5.0,6.0
	
	=============================================================================
	

{% endraw %}
