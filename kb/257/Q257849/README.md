---
layout: page
title: "Q257849: HOWTO: Resize RichTextbox Control with Endless Bottom"
permalink: /kb/257/Q257849/
---

## Q257849: HOWTO: Resize RichTextbox Control with Endless Bottom

{% raw %}

	Article: Q257849
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:5.0,6.0
	Operating System(s): 
	Keyword(s): kbAPI kbCtrl kbRichEdit kbSDKWin32 kbVBp kbVBp500 kbVBp600 kbGrpDSVB
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Learning Edition for Windows, versions 5.0, 6.0 
	- Microsoft Visual Basic Professional Edition for Windows, versions 5.0, 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, versions 5.0, 6.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article demonstrates how to resize the Microsoft Rich Textbox control to
	the size of its contents. For instance, it may be desirable to add a Rich
	Textbox control to a Web page and have the control display its entire contents.
	Another scenario would be to resize the control to either the height of the
	contents or the height of a form.
	
	MORE INFORMATION
	================
	
	This sample demonstrates how to intercept windows messages and check for a
	specific message, EN_REQUESTRESIZE. This is accomplished by creating a message
	handler (hook) and sending an event mask to the parent window. The event mask
	tells the form what type of messages the control is sending. If you are
	unfamiliar with message handlers, please see the "References" section of this
	article.
	
	WARNING: Failure to unhook a window before its imminent destruction results in
	application errors, Invalid Page Faults, and data loss. This is due the fact
	that the new WindowProc function being pointed to no longer exists, but the
	window has not been notified of the change. Always unhook the sub-classed window
	upon unloading the sub-classed form or exiting the application. This is
	especially important while debugging an application that uses this technique
	within the Microsoft Visual Basic Development Environment. Pressing the End
	button or selecting End from the Run menu without unhooking causes an Invalid
	Page Fault and closes Microsoft Visual Basic.
	
	Sample Code
	-----------
	
	1. Start a new Visual Basic Standard EXE project. Form1 is created by default.
	
	2. On the Project menu, select Components. Check the Rich Textbox and Common
	  Dialog controls, and then click OK.
	
	3. Add a CommandButton, a CommonDialog, and a RichTextBox control to Form1.
	
	4. In the Properties window, set the ScrollBars property of RichTextBox1 to
	  "2-rtfVertical" (without the quotation marks).
	
	5. Add the following code to the General Declarations section of Form1:
	
	  Option Explicit
	
	  Private Sub Form_Load()
	  ' Create a Hook and populate a global variable with the Richtextbox hwnd.
	     Call NewWindowProc(Me.hWnd)
	     RichWnd = RichTextBox1.hWnd
	  End Sub
	
	  Private Sub Command1_Click()
	  ' Load a file into the richtextbox control
	     With CommonDialog1
	        .Filter = "All Files|*.*|Text Files|*.txt|RTF Files|*.rtf"
	        .ShowOpen
	        RichTextBox1.FileName = .FileName
	     End With
	  End Sub
	
	  Private Sub Form_Resize()
	  ' 1.)Populate global variables with the Height and Width of the 
	  '   Richtextbox control.
	  ' 2.)Set an event mask for the Richtextbox control.
	  ' 3.)Send an EM_REQUESTRESIZE Message to the Form.
	
	     gblWidth = RichTextBox1.Width / Screen.TwipsPerPixelX
	     gblHeight = ((Form1.Height - RichTextBox1.Top) - 450) / _
	                 Screen.TwipsPerPixelY
	     Call SetMask(RichWnd)
	     Call SendMessage(RichWnd, EM_REQUESTRESIZE, 0, 0)
	  End Sub
	
	  Private Sub Form_Unload(Cancel As Integer)
	     Call ResetWindProc(Me.hWnd) ' Remove the Windows Hook
	  End Sub
	
	6. On the Project menu, select Add Module to add a BAS module to the project.
	  Module1 is created by default.
	
	7. Add the following code to General Declarations section of Module1:
	
	  Option Explicit
	
	  ' Private Variables
	
	  Private rResize As REQSIZE ' <--- Pointer to REQSIZE Structure
	  Private MaskHdr As nmhdr   ' <--- Pointer to nmhdr Structure
	  Private OldWndProc As Long
	  Private Const GWL_WNDPROC = (-4)
	  Private Const WM_USER = &H400
	  Private Const WM_NOTIFY = &H4E
	  Private Const SWP_NOMOVE = &H2
	  Private Const SWP_SHOWWINDOW = &H40
	  Private Const EM_GETEVENTMASK = (WM_USER + 59)
	  Private Const EM_SETEVENTMASK = (WM_USER + 69)
	  Private Const ENM_REQUESTRESIZE As Long = &H40000
	  Private Const EN_REQUESTRESIZE = &H701
	
	  ' Public Variables
	
	  Public gblWidth As Long     ' <--- Var Holder for Richtext Width
	  Public gblHeight As Long    ' <--- Var Holder for Richtext Height
	  Public Const EM_REQUESTRESIZE = (WM_USER + 65)
	  Public Const VBNullPtr = 0&
	  Public RichWnd As Long      ' <--- Var Holder for Richtext Hwnd
	
	  Private Type nmhdr
	     hwndFrom As Long
	     idfrom As Long
	     code As Long
	  End Type
	
	  Private Type rect
	     Left As Long
	     Top As Long
	     Right As Long
	     Bottom As Long
	  End Type
	
	  Private Type REQSIZE
	     nmhdr As nmhdr
	     rect As rect
	  End Type
	
	  Public Declare Function SendMessage Lib "user32" Alias "SendMessageA" _
	     (ByVal hwnd As Long, ByVal wMsg As Long, ByVal wParam As Long, _
	     ByVal lParam As Long) As Long
	
	  Private Declare Function SetWindowLong Lib "user32" Alias _ 
	     "SetWindowLongA" (ByVal hwnd As Long, ByVal nIndex As Long, _ 
	     ByVal dwNewLong As Long) As Long
	
	  Private Declare Function CallWindowProc Lib "user32" _
	     Alias "CallWindowProcA" (ByVal lpPrevWndFunc As Long, _
	     ByVal hwnd As Long, ByVal Msg As Long, ByVal wParam As Long, _
	     ByVal lParam As Long) As Long
	
	  Private Declare Sub CopyMemory Lib "kernel32" Alias "RtlMoveMemory" _
	     (Destination As Any, Source As Any, ByVal Length As Long)
	
	  Public Declare Function SetWindowPos Lib "user32" _
	     (ByVal hwnd As Long, ByVal hWndInsAfter As Long, ByVal x As Long, _
	      ByVal y As Long, ByVal cx As Long, ByVal cy As Long, _
	      ByVal wFlags As Long) As Long
	
	  ' Call SetWindowLong to instantiate the Window Procedure by passing the
	  ' Address of MyWndProc.
	
	  Public Sub NewWindowProc(fhWnd As Long)
	     On Error Resume Next
	     OldWndProc = SetWindowLong(fhWnd, GWL_WNDPROC, AddressOf MyWndProc)
	  End Sub
	
	  ' Once the Hook is in place, All messages will be processed by this
	  ' function. Test for a WM_NOTIFY and parse the lParam to search for a
	  ' specific value. In this case we are looking for EN_REQUESTRESIZE in the
	  ' nmhdr structure. If an EN_REQUESTRESIZE is found then grab the next
	  ' structure(REQSIZE) from the lParam.
	
	  Public Function MyWndProc(ByVal hwnd As Long, _
	                            ByVal Msg As Long, _
	                            ByVal wParam As Long, _
	                            ByVal lParam As Long) As Long
	     On Error Resume Next
	
	     Select Case Msg
	        Case WM_NOTIFY
	           Call CopyMemory(MaskHdr, ByVal lParam, Len(MaskHdr))
	           
	           If MaskHdr.code = EN_REQUESTRESIZE Then
	              Call CopyMemory(rResize, ByVal lParam, Len(rResize))
	
	              If rResize.rect.Bottom < gblHeight Then
	                 Call SetWindowPos(RichWnd, VBNullPtr, _
	                                   0, 0, gblWidth, _
	                                   rResize.rect.Bottom, _
	                                   SWP_SHOWWINDOW Or SWP_NOMOVE)
	
	              Else
	                 Call SetWindowPos(RichWnd, VBNullPtr, _
	                                      0, 0, _
	                                      gblWidth, gblHeight, _
	                                      SWP_SHOWWINDOW Or SWP_NOMOVE)
	              End If
	  ' By modifying 2 of the above parameters you can create an endless bottom
	  ' Richtext control. This may be desirable if you plan to wrap the control
	  ' and use it on a web page. To test this, comment the 'If' Statement above
	  ' and replace it with the SetWindowPos Function call below.
	  ' The control will now Resize itself to its actual contents.
	
	  '               Call SetWindowPos(RichWnd, VBNullPtr, _
	  '                             0, 0, _
	  '                             gblWidth, rResize.rect.Bottom, _
	  '                             SWP_SHOWWINDOW Or SWP_NOMOVE)
	           End If
	              
	        Case Else ' Handle other messages here.
	     End Select
	      
	  ' Reset windowproc
	     MyWndProc = CallWindowProc(OldWndProc, hwnd, Msg, wParam, lParam)
	
	  End Function
	
	  Public Sub ResetWindProc(hwnd As Long)
	
	     On Error Resume Next
	     
	  ' Call SetWindowLong to remove the Windows Hook from app.
	
	     Call SetWindowLong(hwnd, GWL_WNDPROC, OldWndProc)
	
	  End Sub
	
	  Public Sub SetMask(fhWnd As Long)
	     On Error Resume Next
	     Dim CurrentMask As Long
	     Dim NewMask As Long
	  ' Set the Event Mask to be called.
	
	     CurrentMask = SendMessage(fhWnd, EM_GETEVENTMASK, 0, 0)
	     NewMask = (CurrentMask Or ENM_REQUESTRESIZE)
	     Call SendMessage(fhWnd, EM_SETEVENTMASK, 0, ENM_REQUESTRESIZE)
	  End Sub
	
	8. Save and run the project. Note that the control is now being displayed using
	  the height of the contents or the height of the form.
	
	9. Comment out the If statement described in the comments in Module1 of the code
	  sample, and uncomment the SetWindowPos function call following it.
	
	10. Save the project and run it. The RichTextBox control now resizes itself to
	  the height of its contents regardless of the size of the contents.
	
	REFERENCES
	==========
	
	For additional information, click the article number below to view the article
	in the Microsoft Knowledge Base:
	
	  Q170570 HOWTO: Build a Windows Message Handler with AddressOf in VB
	
	  Q168795 HOWTO: Hook Into a Window's Messages Using AddressOf
	
	MSDN Article: Bottomless Rich Edit Controls
	
	Additional query words:
	
	======================================================================
	Keywords          : kbAPI kbCtrl kbRichEdit kbSDKWin32 kbVBp kbVBp500 kbVBp600 kbGrpDSVB 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVB600Search kbVBA500 kbVBA600 kbVB500 kbVB600
	Version           : WINDOWS:5.0,6.0
	Hardware          : x86
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
