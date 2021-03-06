---
layout: page
title: "Q84133: Dlgs.exe Demos Undesirable Interactions Bet. Dialogs"
permalink: /kb/084/Q84133/
---

## Q84133: Dlgs.exe Demos Undesirable Interactions Bet. Dialogs

{% raw %}

	Article: Q84133
	Product(s): Microsoft Windows Software Development Kit
	Version(s): WINDOWS:3.0,3.1
	Operating System(s): 
	Keyword(s): kbfile kbsample kb16bitonly kbDlg kbGrpDSUser kbOSWin310 kbOSWin300
	Last Modified: 05-DEC-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows Software Development Kit (SDK) versions 3.0, 3.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Some combinations of modal and modeless dialog boxes create undesirable side
	effects due to their design and implementation. This article describes the side
	effects and methods to avoid them. The following list of side effects may not be
	complete, and will be updated as additional side effects are discovered.
	
	Side Effects
	------------
	
	1. Unable to change focus with the keyboard if a modeless dialog box is created
	  as the child of an active modal dialog box.
	
	2. Unable to change focus with the keyboard if a modeless dialog box is owned by
	  an active modal dialog box.
	
	3. Input focus moves to another application if a modeless dialog box is
	  destroyed during processing of the WM_INITDIALOG message of a modal dialog
	  box owned by the application's top-level window.
	
	Dlgs.exe is a file in the Microsoft Software Library that demonstrates the three
	side effects listed above, explains the causes of each, and demonstrates the
	method listed below to avoid each problem.
	
	MORE INFORMATION
	================
	
	The following files are available for download from the Microsoft Download
	Center:
	
	Dlgs.exe
	
	For additional information about how to download Microsoft Support files, click
	the article number below to view the article in the Microsoft Knowledge Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	Microsoft used the most current virus detection software available on the date of
	posting to scan this file for viruses. Once posted, the file is housed on secure
	servers that prevent any unauthorized changes to the file.
	
	
	Sections A and B below list some characteristics of the design and implementation
	of modal and modeless dialog boxes. Section C below explains the causes of the
	side effects listed above and techniques to avoid these side effects.
	
	Section A: Characteristics of a Modal Dialog Box
	------------------------------------------------
	
	- A modal dialog box has its own message loop to process messages from the
	  application's queue without involving the application's message loop. This
	  private message loop is active as long as the modal dialog is active.
	
	- A modal dialog box disables its owner to prevent the owner from processing
	  input. By default, a modal dialog box disables only one window; the other
	  windows remain enabled and can process user input unless they are explicitly
	  disabled.
	
	Section B: Characteristics of a Modeless Dialog Box
	---------------------------------------------------
	
	- A modeless dialog box does not disable its owner window. Therefore, the user
	  can continue to work with the owner window while the modeless dialog box is
	  displayed.
	
	- A modeless dialog receives its messages through the application's main
	  message loop.
	
	- An application typically calls the IsDialogMessage() function to process
	  keyboard input for the modeless dialog box. IsDialogMessage() handles
	  changing the focus between controls using the keyboard.
	
	Section C: Explaining the Side Effects
	--------------------------------------
	
	Side Effect 1
	-------------
	
	Symptoms
	
	When a modeless dialog box is created as a child of a modal dialog box, the
	keyboard cannot be used to change the focus.
	
	Cause
	
	The modal dialog box's message loop does not provide the functionality of the
	IsDialogMessage() function.
	
	Resolution
	
	Substitute a modeless dialog box for the modal dialog box. To make the parent
	modeless dialog box appear modal, disable its owner window in the code to
	process the WM_INITDIALOG message.
	
	When a modal dialog box is in its message loop, all windows in the application,
	including each modeless dialog box, receive its messages from the modal dialog
	box's message loop. However, this message loop does not provide the
	functionality of IsDialogMessage().
	
	Side Effect 2
	-------------
	
	Symptoms
	
	When a modeless dialog box is owned by a modal dialog box, the keyboard cannot be
	used to change the focus.
	
	Cause
	
	The modal dialog box's message loop does not provide the functionality of the
	IsDialogMessage() function.
	
	Resolution
	
	Substitute a modeless dialog box for the modal dialog box. To make the parent
	modeless dialog box appear modal, disable its owner window in the code to
	process the WM_INITDIALOG message.
	
	Side Effect 3
	-------------
	
	Symptoms
	
	If a modeless dialog box is destroyed during the processing of the WM_INITDIALOG
	message for a modal dialog box owned by the application's top- level window, the
	focus moves to another application.
	
	Cause
	
	No window is available to receive the focus.
	
	Resolution
	
	Substitute a modeless dialog box for the modal dialog box, as above. Disable the
	owner window (to simulate modality) only after the modeless dialog box is
	destroyed. Then Windows can put the input focus back to the top window until the
	simulated modal dialog box is displayed.
	
	Windows sends a WM_INITDIALOG message to a modal dialog box just before the
	dialog is made visible. As part of destroying a window that has the input focus,
	Windows removes the focus from the window and gives the focus to another window.
	If the new modal dialog box destroys the modeless dialog box as it processes a
	WM_INITDIALOG message, the modal dialog box is not yet visible and cannot
	receive the input focus. Unless the application has other visible windows, the
	only window that can receive the input focus is the top-level window. However,
	because the top-level window owns the new modal dialog box, it is disabled and
	cannot receive the input focus.
	
	Because none of the active application's windows are eligible to receive the
	input focus, Windows activates another application and gives the input focus to
	one of its windows. When this other application receives the focus, it moves to
	the front, over the application that created the modal dialog box. As soon as
	the original application processes the WM_INITDIALOG message, the modal dialog
	box is displayed and brought to the front.
	
	The scenario above causes another application to be "sandwiched" between the
	application's main window and the modal dialog box, which may confuse the user.
	The following diagram illustrates the visual effect:
	
	  +------------------------------------------------------------+
	  |         Application 1's Main Window                        |
	  |  +-------------------------------------------------------+ |
	  |  |       Application 2's Main Window                     | |
	  |  |       (on top of application 1's main window)         | |
	  |  | +---------------------------------------------------+ | |
	  |  | |      Application 1's Modal Dialog                 | | |
	  |  | |      (on top of application 2)                    | | |
	  |  | |                                                   | | |
	  |  | +---------------------------------------------------+ | |
	  |  +-------------------------------------------------------+ |
	  +------------------------------------------------------------+
	
	Additional query words:
	
	======================================================================
	Keywords          : kbfile kbsample kb16bitonly kbDlg kbGrpDSUser kbOSWin310 kbOSWin300 
	Technology        : kbAudDeveloper kbWin3xSearch kbSDKSearch kbWinSDKSearch kbWinSDK300 kbWinSDK310
	Version           : WINDOWS:3.0,3.1
	
	=============================================================================
	

{% endraw %}
