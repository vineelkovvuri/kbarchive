---
layout: page
title: "Q138735: FAQ: Visual C++ 4.0 Frequently Asked Questions"
permalink: /kb/138/Q138735/
---

## Q138735: FAQ: Visual C++ 4.0 Frequently Asked Questions

{% raw %}

	Article: Q138735
	Product(s): Microsoft C Compiler
	Version(s): WINNT:4.0;
	Operating System(s): 
	Keyword(s): kbtshoot kbGenInfo kbVC kbArtTypeINFkbfaq
	Last Modified: 30-JUL-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual C++, version 4.0 
	-------------------------------------------------------------------------------
	
	Q. I just ported my Visual C++ 2.x project to Visual C++ 4.0. What happened
	  to my program group folders?
	
	A.  With Visual C++ 2.x, you could organize files within a project by
	  creating groups and adding source files to them. Visual C++ 4.0 does not
	  support this feature. If you convert a project from Visual C++ 2.x to
	  Visual C++ 4.0, the newly created project will retain all settings for
	  files in any Visual C++ 2.x groups, but it does not mark or group these
	  files in any way. Developer Studio now supports multiple projects and
	  subprojects, which may provide you with some grouping functionality. You
	  can still set settings for multiple files by invoking the Project
	  Settings dialog box and selecting multiple files from the "Settings
	  For:" tree control.
	
	===============================================================================
	
	Q. My video card supports 16K or more colors. Why can't Developer Studio
	  open my 256 color bitmaps?
	
	A.  The Developer Studio bitmap editor in Visual C++ 4.0 does not currently
	  support color setting configurations greater than 256 colors. If your
	  video card is configured to display more than 256 colors and you attempt
	  to open a 256 color bitmap, the following error message will be
	  displayed:
	
	  C:\filename.bmp
	  Cannot load file
	
	  The current display device does not support the palettes that are
	  required for editing 256-color bitmaps. To work around this limitation,
	  reset the Color Palette to 256 colors in the Control Panel's Display
	  settings dialog box.
	
	===============================================================================
	
	Q. Where is the documentation for the OLE Controls that ship with Visual
	  C++ 4.0?
	
	A.  The OLE Controls that ship with Visual C++ 4.0 are documented in the
	  Ctrlref.hlp and Vb.hlp help files located in the \Msdev\Help directory.
	  To gain access to these help files from Developer Studio, use one of the
	  following methods:
	  
	
	1. From the Component Gallery dialog box, select a specific control, and then
	  click the help '?' button to invoke the help topic for the selected control.
	
	  -or-
	
	2. For help for a particular control, use the Dialog Editor. Place the desired
	  control on a dialog box, and invoke the Properties dialog box for the
	  control. Then click the Control tab from the Properties dialog box, and press
	  F1.
	
	  -or-
	
	3. Add these help files to your F1 help in Developer Studio. Please see the
	  \Msdev\Help\Exthelp.hlp help file for details on how to accomplish this.
	
	===============================================================================
	
	Q. How do I prevent classes from being displayed in the ClassView pane of
	  the Workspace window?
	
	A.  To prevent classes from being displayed in the ClassView pane, you need
	  to remove the header with the class declarations from the project's
	  dependency list. To do this, follow these steps:
	
	1. Create a directory in which to relocate the header file(s) that you want to
	  remove from the dependency list. For example:
	
	  mkdir c:\msdev\projects\myproj\inc
	
	2. Move the header files to this new directory.
	
	3. Add this directory to your include search path by using the Directories page
	  of the Options dialog box invoked by clicking Options on the Tools menu.
	
	4. Create a text file named Msvcincl.dat, and list the header files you want to
	  exclude from the dependencies list. Do not include the path names to the
	  header files. Save this file to your Windows directory.
	
	5. Close Developer Studio, and delete the project's .ncb file.
	
	6. Restart Developer Studio, and load your project. The classes declared in the
	  headers listed in the Msvcincl.dat file should no longer appear in the
	  ClassView pane.
	
	  NOTE: The Msvcincl.dat file must be located in your Windows directory, and
	  your #include directives must not specify a full pathname to these headers.
	  Otherwise, these files will remain in the project's dependencies list.
	
	===============================================================================
	
	Q. New projects created with Visual C++ 4.0 seem to build faster than
	  projects ported from earlier versions of Visual C++. What can I do to
	  decrease the build time for these older projects?
	
	A.  In Visual C++ 4.0, wizard-generated applications automatically add a
	  macro definition for VC_EXTRALEAN to the project's precompiled header.
	  This macro also defines the macros WIN32_LEAN_AND_MEAN and
	  WIN32_EXTRA_LEAN. These macros define subsequent macros that exclude
	  less-used declarations from the various Windows header files, to help
	  speed compilation. For complete information on what these macros
	  exclude, search the Windows.h and Afx_w32.h files for these symbols. To
	  use this macro in your older projects, add the following to the top of
	  your project's precompiled header file (typically Stdafx.h for most MFC
	  applications):
	
	     #define VC_EXTRALEAN
	
	===============================================================================
	
	Q. Why aren't the breakpoints in my project being recognized?
	
	A.  Please read the "PRB: Breakpoints Won't Work - 11 Reasons Why" Microsoft
	  Knowledge Base article located in Books Online. If you are attempting to
	  debug an OLE control, make sure the debug version of the control is
	  registered. If you build and register a release version of the control,
	  and then attempt to debug the debug version of the control, the release
	  version of the OLE Control will inadvertently be used.
	
	===============================================================================
	
	Q. I inserted an OLE control into my project with Component Gallery, and
	  now the compiler reports the following error messages when I attempt to
	  build my project: "C2501: missing decl-specifier," "C2504: base class
	  undefined," and "C2065: undeclared identifier." What's wrong with my
	  project?
	
	A.  You probably didn't enable OLE control support when you first built your
	  application. You can easily add OLE control support to your existing
	  project by using the Component Gallery. Just insert the OLE Control
	  Containment component into your project. This will add an include
	  statement for Afxdisp.h to the project's pre-compiled header, and a call
	  to AfxEnableControlContainer() in your CWinApp-derived object's
	  InitInstance() function. For additional information on how to use OLE
	  controls in your application, please see the "OLE Control Containers:
	  Inserting a Control into a Control Container Application" Help topic.
	
	===============================================================================
	
	Q. Where are the .mak and/or .mdp files for the SDK samples in Help?
	
	A.  With the exception of the CROSSDEV samples, the Windows SDK samples do
	  not ship with .mak or .mdp files. These samples are included directly
	  from the Win32SDK samples. Each sample includes a makefile named
	  MAKEFILE that can be used to build the accompanying sample. Upon
	  attempting to open the MAKEFILE with Developer Studio, you will be
	  prompted to wrap the existing makefile. If you continue, Developer
	  Studio will create a new internal .mak file that will wrap the existing
	  MAKEFILE. You can build the sample by using this new .mak file, or
	  invoke NMAKE from a command prompt. To invoke NMAKE from a command
	  prompt, you first need to change your current directory to the project
	  directory, and you may need to run the \Msdev\Bin\Vcvars32.bat file to
	  properly set up the environment.
	
	  NOTE: If you wrap the MAKEFILE, you can add the source files to the new
	  project to allow for easy viewing and editing.
	
	===============================================================================
	
	Q. How do I create a subproject based on an existing project?
	
	A.  Visual C++ 4.0 does not support the creation of subprojects based on
	  existing projects. For example, if you have an existing MFC DLL project
	  that you would like to fold into an MFC application workspace, you can
	  either create a new skeleton project and merge your existing sources
	  with this new project, or you can use a batch file to change the working
	  directory, and invoke NMAKE on the subproject you want to build. To
	  accomplish this, do the following:
	
	1. On the Build menu, click Subprojects, and then click New.
	
	2. From the Insert Project dialog box, select a Project of type Makefile.
	  Specify a project name and whether or not it's to become a subproject of an
	  existing project.
	
	3. Click Create, and then click Yes. This takes you directly to the Project
	  Settings dialog box for this new project.
	
	4. Specify a build command line to invoke a batch file for this new project. You
	  will want to do this for both the debug and release configurations. Specify a
	  unique batch file for each configuration you may have, or pass the required
	  NMAKE command line options to the batch file, so you can support building
	  your subproject for multiple targets using NMAKE macros.
	
	5. Write the batch file to change the working directory to that of the original
	  project directory, and then invoke NMAKE on the project's .mak file.
	
	===============================================================================
	
	Q. Why can't I edit EXE resources running Developer Studio under Windows
	  95?
	
	A.  Developer Studio now supports the direct editing of resources within an
	  .exe file but only under Windows NT. Windows NT provides APIs that allow
	  you to modify resources in an executable (.exe) file or dynamic link
	  library (.dll) file. Windows 95 does not support the APIs necessary to
	  do this. For example, Windows 95 does not support BeginUpdateResource(),
	  UpdateResource(), or EditUpdateResource(). When a resource is loaded
	  under Windows 95, Developer Studio will issue the following warning:
	
	  Microsoft Developer Studio cannot save the modified resources back to
	  this executable. The executable may be in use, or this version of
	  Windows may not support updated resources in executables.
	
	  While the executable cannot be modified in Windows 95, the resources can
	  be copied into an .rc file
	
	======================================================================
	Keywords          : kbtshoot kbGenInfo kbVC kbArtTypeINF kbfaq
	Technology        : kbVCsearch kbVC400 kbAudDeveloper
	Version           : WINNT:4.0;
	
	=============================================================================
	

{% endraw %}
