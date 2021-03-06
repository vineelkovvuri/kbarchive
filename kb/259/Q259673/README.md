---
layout: page
title: "Q259673: HOWTO: Change the Application Icon with Visual Basic"
permalink: /kb/259/Q259673/
---

## Q259673: HOWTO: Change the Application Icon with Visual Basic

{% raw %}

	Article: Q259673
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:4.0,5.0,6.0
	Operating System(s): 
	Keyword(s): kbAPI kbIcon kbSDKWin32 kbVBp kbVBp400 kbVBp500 kbVBp600 kbWndwMsg kbGrpDSVB kbDSupport
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Standard Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition for Windows, versions 5.0, 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, versions 5.0, 6.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Sometimes you may want to change the icon associated with an application. This
	application icon is what appears when you use the ALT+TAB key combination to
	switch between applications that are currently running on your computer. The
	icon can be changed by using the SendMessage API function.
	
	MORE INFORMATION
	================
	
	All Visual Basic applications have an invisible top-level window that processes
	events and messages. In design mode, the window is ThunderMain, in run mode, the
	window is ThunderRT6Main. The RT6 reflects the version of Visual Basic that is
	being used. Both windows have the name of the project, or the executable name as
	the window caption. This is where the application icon is set.
	
	You need to use the GetWindowLong function to walk up the window chain until the
	function returns a 0, indicating that there are no more parent windows.
	Alternatively, you could search for ThunderRT6Main with the FindWindow API
	function, but there might be more than one instance of your application.
	(FindWindow searches for a window based on it's window class name and/or the
	window text. If there are two instances of the application, both windows are
	exactly the same. Therefore, it's not certain that you always find the one that
	you are actually working with.)
	
	The following Visual Basic sample demonstrates this.
	
	When you set the Icon property, you can get the source Icon in several ways:
	
	- By using the Picture property of a PictureBox control (as demonstrated
	  later).
	
	- By using the LoadPicture function to load the Icon from an .ico file. For
	  example:
	
	  Set Me.Icon = LoadPicture("C:\Program Files\Microsoft Visual " _
	        & "Studio\Common\Graphics\Icons\Misc\BULLSEYE.ICO")
	
	- By using the LoadResPicture function to load the Icon from a resource (.res)
	  file. For example:
	
	  Set Me.Icon = LoadResPicture(101, vbResIcon)
	
	Step-by-Step Example
	--------------------
	
	1. Start a new Standard EXE project in Visual Basic. Form1 is created by
	  default.
	
	2. From the Project menu, add a new module to the project.
	
	3. Add the following API declarations to Module1:
	
	  Option Explicit
	
	  Public Declare Function GetWindowLong Lib "user32" Alias "GetWindowLongA" _
	      (ByVal hWnd As Long, ByVal nIndex As Long) As Long
	  Public Declare Function SendMessage Lib "user32" Alias "SendMessageA" _
	      (ByVal hWnd As Long, ByVal wMsg As Long, ByVal wParam As Long, lParam As Any) As Long
	  Public Declare Function LoadIcon Lib "user32" Alias "LoadIconA" _
	      (ByVal hInstance As Long, lpIconName As Any) As Long
	
	  Public Const GWL_HWNDPARENT = (-8)
	
	  Public Const WM_GETICON = &H7F
	  Public Const WM_SETICON = &H80
	
	  Public Const ICON_SMALL = 0
	  Public Const ICON_BIG = 1
	
	4. Click on Form1 and set an icon in the Properties window. This becomes the
	  default application icon.
	
	5. Add a PictureBox control to Form1.
	
	6. Click the Picture property and click the ellipsis (...) button. This allows
	  you to choose which picture you want to put in the PictureBox. Choose an icon
	  (.ico) file extension.
	
	7. Add a CommandButton control to Form1.
	
	8. Add the following code to the code window of Form1:
	
	  Private nRet         As Long
	  Private nMainhWnd    As Long
	
	  Private Sub Form_Load()
	      nRet = GetWindowLong(Me.hWnd, GWL_HWNDPARENT)
	      Do While nRet
	         nMainhWnd = nRet
	         nRet = GetWindowLong(nMainhWnd, GWL_HWNDPARENT)
	      Loop
	  End Sub
	
	  Private Sub Command1_Click()
	      Dim hIcon As Long
	      
	      ' set the icon
	      Set Me.Icon = Picture1.Picture
	      ' get a handle to ICON_BIG
	      hIcon = SendMessage(Me.hWnd, WM_GETICON, ICON_BIG, ByVal 0)
	      ' send ICON_BIG to the main window
	      SendMessage nMainhWnd, WM_SETICON, ICON_BIG, ByVal hIcon 
	  End Sub
	
	9. Compile the project and run the new executable file. Press the ALT+TAB key
	  combination to see what your application icon is. If you are testing this in
	  the Visual Basic IDE, note that the default Microsoft Windows icon appears.
	
	10. Click the CommandButton and press ALT+TAB again. Note that the application
	  icon has changed.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbAPI kbIcon kbSDKWin32 kbVBp kbVBp400 kbVBp500 kbVBp600 kbWndwMsg kbGrpDSVB kbDSupport 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVB600Search kbVBA500 kbVBA600 kbVB500 kbVB600 kbVB400Search kbVB400
	Version           : WINDOWS:4.0,5.0,6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
