---
layout: page
title: "Q138066: HOWTO: Handle OLE Automation Server Timeout and Synchronization"
permalink: /kb/138/Q138066/
---

## Q138066: HOWTO: Handle OLE Automation Server Timeout and Synchronization

{% raw %}

	Article: Q138066
	Product(s): Microsoft Visual Basic for Windows
	Version(s): 
	Operating System(s): 
	Keyword(s): kbGrpDSVB
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Learning Edition for Windows, version 6.0 
	- Microsoft Visual Basic Professional Edition for Windows, version 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 6.0 
	- Microsoft Visual Basic Professional Edition for Windows, version 5.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 5.0 
	- Microsoft Visual Basic Standard Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 32-bit, for Windows, version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	There are seven properties of the App object that allow you to handle the timing
	and synchronization of OLE calls made from a Visual Basic client to an OLE
	automation server:
	
	OLERequestPendingTimeout
	OLERequestPendingMsgText
	OLERequestPendingMsgTitle
	OLEServerBusyTimeOut
	OLEServerBusyMsgText
	OLEServerBusyMsgTitle
	OLEServerBusyRaiseError
	
	MORE INFORMATION
	================
	
	Client calls to methods or properties on OLE Automation Servers are synchronous;
	that is, the calls do not return until the particular procedure has finished.
	This might be an issue if a particular call takes so long that the user starts
	clicking the mouse or pressing the keyboard to elicit some response. The user
	may then falsely conclude that the application is not working when, in fact, it
	is only busy. This situation might appear even more confusing when the OLE
	Automation server is invisible. Under such circumstances, OLE brings up a dialog
	box displaying a cryptic message that the server is busy.
	
	The OLERequestPendingMsgText and OLERequestPendingMsgTitle properties can be used
	to customize the message actually displayed under these circumstances to better
	reflect the actual situation, and the length of time after which the message
	will be displayed can be controlled by the OLERequestPendingTimeout property.
	
	A similar message will be displayed when the OLE server rejects an OLE Automation
	request from a client. The client will keep trying until the number of
	milliseconds specified in the OLEServerBusyTimeOut property has elapsed. The
	OLEServerBusyMsgText and OLEServerBusyMsgTitle properties allow you to customize
	the actual messages displayed.
	
	The OLEServerBusyRaiseError property determines whether a rejected OLE Automation
	request raises an error instead of displaying a "busy" message. Raising an error
	when an OLE server rejects an OLE Automation request returns control to your
	program, which allows you to provide your own custom dialog box in place of
	either the default Server Busy dialog box or the customized busy message. The
	OLE Automation error that will be raised is -2147418111 (&h80010001)
	
	The App object implements these properties by supporting the IMessageFilter OLE
	interface. Please refer to the OLE Programmer's Reference for more details on
	this interface.
	
	Additional query words: kbVBp400 kbVBp500 kbVBp600 kbVBp kbdsd kbDSupport kbAutomation kbInterop 
	kbOLE
	
	======================================================================
	Keywords          : kbGrpDSVB 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVB600Search kbVBA500 kbVBA600 kbVB500 kbVB600 kbVB400Search kbVB400 kbVB16bitSearch
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
