---
layout: page
title: "Q176876: HOWTO: Find VB32.EXE Without Searching the Hard Drive"
permalink: /kb/176/Q176876/
---

## Q176876: HOWTO: Find VB32.EXE Without Searching the Hard Drive

{% raw %}

	Article: Q176876
	Product(s): Microsoft Visual Basic for Windows
	Version(s): 
	Operating System(s): 
	Keyword(s): kbGrpDSVB
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Professional Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 32-bit, for Windows, version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The sample code below demonstrates how to find the location of VB32.EXE by
	checking the registry rather than searching the entire hard drive.
	
	MORE INFORMATION
	================
	
	Because customers occasionally install Visual Basic with a pathname other than
	the default suggested by SETUP, it may be necessary to search for the directory
	in which VB32.EXE has been installed. While simply searching the local hard
	drive with an equivalent to DIR/S serves in most circumstances, the presence of
	multiple large volumes makes a brute-force search of all the directories on each
	volume impractical.
	
	Because Visual Basic Setup stores the fully-qualified path name to VB32.EXE under
	the key:
	
	"HKEY_LOCAL_MACHINE\Software\Classes\VisualBasic\Shell\Open\command,"
	
	it is a fairly simple task to obtain that pathname with the RegQueryValueEx()
	API.
	
	Step-By-Step Instructions
	-------------------------
	
	1. Open a new project. Form1 is created by default.
	
	2. Add a Code Module and, in the General Declarations section, place the
	  following code:
	
	     Declare Function RegOpenKeyEx Lib "advapi32.dll" Alias "RegOpenKeyExA" _
	     (ByVal hKey As Long,  ByVal lpSubKey As String, ByVal ulOptions As _
	     Long, ByVal samDesired As Long, phkResult As  Long) As Long
	
	     Declare Function RegQueryValueEx Lib "advapi32.dll" Alias _
	     "RegQueryValueExA" (ByVal hKey As Long, ByVal lpValueName As _
	     String, ByVal lpReserved As Long, lpType As Long, lpData As Any, _
	     lpcbData As Long) As Long
	
	     Option Explicit
	
	     Global Const HKEY_LOCAL_MACHINE = &H80000002
	     Global Const KEY_READ = &H20019
	     Global Const ERROR_SUCCESS = 0&
	
	3. Add a CommandButton to the default form.
	
	4. In the Click Event of the CommandButton, place the following code:
	
	     Dim RegKeyHandle As Long
	     Dim RetVal As Long
	     Dim KeyType As Long
	     Dim Data As String * 255
	     Dim DataLen As Long
	
	     RetVal = RegOpenKeyEx(HKEY_LOCAL_MACHINE, _
	     "Software\Classes\VisualBasic\Shell\Open\command", _
	     0, KEY_READ, RegKeyHandle)
	
	     If RetVal <> ERROR_SUCCESS Then
	         MsgBox "Can't Open Key"
	     Else
	         MsgBox "Opened It!" & vbCrLf & "Getting Default Value"
	         DataLen = 512
	         RetVal = RegQueryValueEx(RegKeyHandle _
	                                 , vbNullString _
	                                 , 0 _
	                                 , KEY_READ _
	                                 , ByVal Data _
	                                 , DataLen)
	
	         If RetVal <> ERROR_SUCCESS Then
	             MsgBox "Missed It!"
	         Else
	             MsgBox Left(Data, DataLen)
	         End If
	     End If
	
	5. Run the program. If Visual Basic is installed, the fully-qualified pathname
	  to VB32.EXE appears in the message box.
	
	REFERENCES
	==========
	
	"Visual Basic Programmer's Guide to the Win32 API", Daniel Appleman, PC Magazine
	Press; c1996.
	
	Additional query words: kbVBp400 kbVBp kbdsd kbDSupport
	
	======================================================================
	Keywords          : kbGrpDSVB 
	Technology        : kbVBSearch kbAudDeveloper kbVB400Search kbVB400
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
