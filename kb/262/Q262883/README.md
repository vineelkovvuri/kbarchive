---
layout: page
title: "Q262883: SAMPLE: NEWVBTERM.EXE MSComm Control Techniques"
permalink: /kb/262/Q262883/
---

## Q262883: SAMPLE: NEWVBTERM.EXE MSComm Control Techniques

{% raw %}

	Article: Q262883
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:6.0
	Operating System(s): 
	Keyword(s): kbfile kbprogramming kbsample kbCtrl kbVBp600 kbGrpDSVB kbDSupport
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Professional Edition for Windows, version 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 6.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	NewVBTerm.exe is a sample that demonstrates various MSComm control techniques
	that include answering the modem, simple text file transfer, data receipt and
	processing, packet reassembly, and use of the OnComm event.
	
	This article contains the Readme file information that accompanies the sample and
	is also a reference point for downloading the sample.
	
	MORE INFORMATION
	================
	
	The following file is available for download from the Microsoft Download
	Center:
	
	  NewVBTerm.exe
	  (http://download.microsoft.com/download/vb60pro/sample1/600/win98/en-us/NewVBTerm.exe
	  )
	
	Release Date: Jun-08-2000
	
	For additional information about how to download Microsoft Support files, click
	the article number below to view the article in the Microsoft Knowledge Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	Microsoft used the most current virus detection software available on the date of
	posting to scan this file for viruses. Once posted, the file is housed on secure
	servers that prevent any unauthorized changes to the file.
	
	NewVBTerm.exe - Readme.txt
	--------------------------
	
	The purpose of this Readme file is to discuss in greater detail how to use and
	interpret the NewVBTerm sample program. This description goes over all of the
	menu items and discusses the functionality of each item.
	
	General:
	
	This application has been designed more as a sample app for various MSComm
	control techniques than a true "Terminal" application. These techniques include
	answering the modem, simple text file transfer, data receipt and processing,
	packet reassembly, and use of the OnComm event.
	
	frmNewTerm:
	
	General UI
	
	The form consists of a main text box that displays all events and other text.
	There are also "status lights" that give the state of the Comm port and the CD,
	RTS, and CTS lines as well as the Send and Receive events.
	
	There is a button labeled Send that appears when you are connected to another
	computer. This sends the contents of the text box out of the Comm port to the
	remote computer.
	
	There is a status bar at the bottom of the form that displays text messages about
	the state of the application.
	
	The form also contains the following menu choices:
	
	File Menu
	
	  Transmit File - Used to transmit text files to another application that can
	  handle file transfer, typically another instance of NewVBTerm. NewVBTerm has
	  been designed specifically to handle this type of transfer. When a file is
	  actually being transmitted, the status light turns Cyan (greenish-blue) in
	  color.
	
	  Receive File - Used in conjunction with the Transmit File menu item to
	  transfer files between two computers. This menu item is checked when in
	  receive mode, unchecked at all other times. In order to complete a file
	  transfer when the file is finished transmitting the form to the sender side,
	  click Receive File again (to unchecked state). This closes and saves the
	  received file.
	
	  Clear Text Box - Erases the contents of the main terminal text box.
	
	  Show Events - Lists all OnComm events in the main terminal text box when
	  checked.
	
	  Show Received Data - Displays all data received by the MSComm control in the
	  main terminal text box when checked.
	
	  Exit - Closes all open ports and terminates the application.
	
	Comm Port Menu
	
	  Open Port - Opens the Comm port without dialing a number. Used for null modem
	  cables and receiving files.
	
	  Close Port - Closes the Comm port.
	
	  Settings - Brings up the Settings form (frmControlProps). This form is
	  discussed later in this article.
	
	  Options - Bring up frmOptions, which is also discussed later in this article.
	
	Dial Menu
	
	  Dial Number - Opens the Comm port (if necessary), prompts the user for a
	  phone number to dial, and then dials it.
	
	  Hang Up - Disconnects the session and closes the Comm port.
	
	  Answer Mode - Opens the port and places it in answer mode, where a call can be
	  answered when another modem dials it.
	
	frmOptions:
	
	There are two sets of two choices each on this form. The top-most is Startup
	Options, which loads either the default values at startup or the "recommended"
	values the next time the app is started.
	
	The second set of options is the modem type. Choose Null Modem cable if you are
	using a null modem cable because this allows for direct connection.
	
	The Return button takes you back to the main form.
	
	frmControlProps:
	
	General UI
	
	There are two columns displayed. The left-hand column of text boxes is filled
	with the current settings of the MSComm control. The text on the right is the
	Microsoft "recommended" values for the MSComm control. The recommended values
	are those that are most likely to enable the user to establish a modem
	connection. Keep in mind that the recommended settings may not work for your
	system without several changes.
	
	In addition, there are two menu items available on the form:
	
	File Menu
	
	  Back to Terminal - Closes the form and returns to the main form (frmNewTerm).
	  The settings shown in the text boxes are also saved as "session only"
	  settings.
	
	Values Menu
	
	  Load defaults - Loads the default settings that are saved in the registry by
	  the Save as defaults menu item.
	
	  Save as defaults - Saves the currently displayed values as the defaults. These
	  settings are stored in the registry under
	
	  HKEY_USERS\.Default\Software\VB
	
	  -and-
	
	  VBA Program Settings\NewVBTerm\Properties\
	
	  Save for session only - Saves the settings indicated in the text boxes to the
	  MSComm control. It does not save any of the settings to the registry. These
	  settings are lost after exiting the program.
	
	  Set recommended values - Loads the MSComm control with the above-mentioned
	  Microsoft recommended settings. The settings are not saved to the registry
	  unless you choose Save as defaults.
	
	Clicking the button labeled Close closes the form and returns you to the main
	form (frmNewTerm). The settings shown in the text boxes are also saved as
	session only settings.
	
	Additional query words: vbterm newvbterm
	
	======================================================================
	Keywords          : kbfile kbprogramming kbsample kbCtrl kbVBp600 kbGrpDSVB kbDSupport 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB600Search kbVBA600 kbVB600
	Version           : WINDOWS:6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
