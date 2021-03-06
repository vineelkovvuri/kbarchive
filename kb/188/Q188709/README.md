---
layout: page
title: "Q188709: Vfpcom.exe Using COM Language Enhancements in VFP 6.0"
permalink: /kb/188/Q188709/
---

## Q188709: Vfpcom.exe Using COM Language Enhancements in VFP 6.0

{% raw %}

	Article: Q188709
	Product(s): Microsoft FoxPro
	Version(s): 6.0
	Operating System(s): 
	Keyword(s): kbfile kbSample kbCOMt kbvfp600 kbGrpDSFox kbDSupport
	Last Modified: 19-OCT-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, version 6.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Vfpcom.exe is a sample that shows how to use the new COM server functions and
	properties added to Visual FoxPro 6.0. This sample goes through each function
	separately and explains why you would want to use them. To use the files,
	extract them into a new directory and follow the instructions in the enclosed
	Readme.txt file.
	
	MORE INFORMATION
	================
	
	The following files are available for download from the Microsoft Download
	Center:
	
	  Vfpcom.exe
	  (http://download.microsoft.com/download/vfox60/sample11/1/W9X/EN-US/Vfpcom.exe)
	
	For additional information about how to download Microsoft Support files, click
	the article number below to view the article in the Microsoft Knowledge Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	Microsoft used the most current virus detection software available on the date of
	posting to scan this file for viruses. Once posted, the file is housed on secure
	servers that prevent any unauthorized changes to the file.
	
	This client server sample demonstrates the new COM functions and commands in
	Visual FoxPro 6.0. These functions make it easier to create robust COM Servers
	in Visual FoxPro. The table below lists the functions used in this sample:
	
	  Function or Command       Description
	  ------------------------------------------------------------------------
	
	  CreateObjectEx()          Used to instantiate remote COM servers.
	
	  COMClassInfo()            Returns information on COM servers.
	
	  COMArray()                Allows you to pass Visual FoxPro arrays to COM
	                            objects by reference or by value.
	
	  COMReturnError()          Allows you to customize and return an error
	                            message to the client.
	
	  SYS(2335)                 Unattended Server Mode disallows any user
	                            interface (UI) display in an Out of
	                            Process COM Server.
	
	  SYS(2334)                 Returns how a COM Server was created, either>
	                            VTable Binding or IDispatch.
	
	  ServerName Property       Holds the full path and file name of the COM
	                            Server.
	
	  StartMode Property        Returns a numeric value indicating how the COM
	                            Server was started.
	
	Steps to Install Sample Files
	-----------------------------
	
	After extracting the files into a new directory, follow the steps below to
	install and run the sample code:
	
	1. In the new directory there is a file named Foxserver.exe. For the sample to
	  work correctly, the Foxserver.exe file must first be registered. The
	  registration may be on a remote or on a local computer.
	
	  To register the Foxserver.exe file:
	
	  a. Copy the files Foxserver.exe, Foxserver.tlb, and Foxserver.vbr to a new
	     directory on the remote computer or leave them in the current directory on
	     the local computer. If you are going to run the sample remotely then you
	     need to copy the run-time files to the new directory as well. The two
	     files you need are Vfp6r.dll and Vfp6renu.dll.
	
	  b. In Windows 95 or Windows NT, click the Start button, and then click RUN.
	     In the RUN dialog box, type the following command:
	
	X:\<New Directory>\Foxserver.exe -REGSERVER
	
	X:\<New Directory> is the location (drive and path) of the .exe file.
	
	NOTE: To unregister the COM server, type the following command in the RUN dialog
	box:
	
	X:\<New Directory>\Foxserver.exe -UNREGSERVER
	
	2. In the FoxPro development environment, set the default directory to the
	  directory in which you extract the files. Now, open the Comsample.pjx
	  project.
	
	3. Run the Comsample.prg file.
	
	4. A top level form that has three tabs appears. This is the client application
	  that communicates with the Foxserver.exe file.
	
	A description of each tab and how it works follows.
	
	Start COM Server Tab
	--------------------
	
	There are two option buttons that allow the COM Server to start either as a
	remote server or a local server.
	
	1. If you register and copy the file to a remote computer, you may start it as a
	  remote COM server. Selecting the remote option enables a text box and a combo
	  box.
	
	2. In the text box, type the name of the remote computer on which you copy the
	  .exe file. This may also be an Internet Protocol (IP) address or a Hypertext
	  Transfer Protocol (HTTP) address. For this sample, use the computer name.
	
	3. In the combo box, select either the ProgID or ClassID of the COM server. If
	  the .exe file is not registered on the local computer and only registered on
	  the remote computer, select the ClassID which is
	  {2468F5C2-069D-11D2-AC3F-00C04FB9D24B}. This ClassID may change if you
	  rebuild the FOXSERVER project and may require manual entry of the ClassID.
	  However, if you do not rebuild the project the preceding value will always be
	  the ClassID.
	
	  If the .exe file was registered on both the local and remote computer then you
	  can choose the ProgID, Foxserver.Comtest. The name changes only if you change
	  the name of the class.
	
	4. Click the Start COM Server button.
	
	  This calls the new CREATEOBJECTEX() or the CREATEOBJECT() function, depending
	  on whether you select remote or local. The CreateObjectEX() function
	  instantiates COM Objects on remote computers without having to run the Remote
	  Automation Manager. This makes remote COM servers easier to setup and run in
	  Visual FoxPro 6.0. In Visual FoxPro 5.0, to run a Visual FoxPro COM Server
	  remotely, you have to use the Remote Automation Manager to register the .exe
	  file and tell it on which remote computer the .exe file is located. However,
	  with CreateObjectEx() you do not have to use the Remote Automation Manager.
	  If you know the ClassID you also do not have to register the COM Server on
	  the local computer.
	
	5. Starting the COM Server populates the "StartMode of the Fox COM Server" text
	  box with the value returned from the new STARTMODE property. This property
	  actually holds a numeric value zero (0) through four (4) This sample uses "2:
	  Out of Process COM Server". You may use this property to determine how your
	  Visual FoxPro application was started and respond accordingly. For example,
	  if your application starts as an Out of Process COM Server, then you may not
	  want any UI to appear. However, if it starts as a standalone application,
	  then you would want the UI to display.
	
	Server Info Tab
	---------------
	
	This tab shows the information you can receive about your COM server through the
	COMClassInfo() function, ServerName property, and SYS(2334) function.
	
	The COMClassInfo() function takes a numeric parameter, 1 through 4, which returns
	the ProgID, Version Independent ProgID, Friendly Name, and Class ID. If the COM
	Server runs remotely and is not registered on the local computer, the first
	three items are blank because you are going right to the ClassID information in
	the registry and skipping the ProgID information. You can use this function to
	obtain the ClassID for the CreateObjectEx() function by registering the COM
	Server locally. You use CreateObject() to instantiate the object and then issue
	COMClassInfo() and pass 4 as the parameter.
	
	The ServerName property returns the full path and file name of the COM Server and
	is useful for pathing to remote data or getting to other files on the remote
	server.
	
	The SYS(2334) function returns a numeric value, zero (0) through two (2), on how
	the COM Server was instantiated. Either by VTable binding or by IDispatch. This
	sample uses IDispatch since Visual FoxPro 6.0 does not support early binding
	(VTable) of COM servers. Visual FoxPro 6.0 does support early binding of COM
	Controls. Please see the Help topic for the SYS(2333) function for more
	information. If you use Visual Basic to instantiate the COM Server and use early
	binding, SYS(2334) returns a one (1).
	
	Error Handling and Passing Arrays Tab
	-------------------------------------
	
	1. One of the error handling improvements in Visual FoxPro 6.0 is the
	  COMReturnError() function. In the sample, if you type an error code in the
	  text box, such as 1, and click the Generate Error button, a friendly error
	  message is returned. In Visual FoxPro 5.0, a cryptic OLE error message is
	  returned and it is harder to trouble shoot the COM Server. Using the
	  COMReturnError() function allows you to return helpful error messages back to
	  the client. Below is code from the Error event in the COMTest class from the
	  FOXSERVER project, which shows the use of COMReturnError() function:
	
	        LPARAMETERS nError, cMethod, nLine
	
	        x="Error "+ALLTRIM(STR(nError))+": " + Message() ;
	           +" occurred in method "+cMethod ;
	           +" on line "+ALLTRIM(STR(nLine)) ;
	           +" This is my very own error message!"
	        COMReturnError("FoxServer.dll",x)
	
	  The first parameter of COMReturnError() describes where the error occurs and
	  the second parameter describes the error. The sample uses the standard error
	  number, Message() and line number as the message.
	
	2. Another error handling improvement in Visual FoxPro 6.0 is the SYS(2335)
	  function, which turns on and off the Unattended Server Mode for Out of
	  Process COM Servers. In the sample, if you select the check box to turn on
	  Unattended Server Mode and click on the button "Generate UI on Server" an
	  error message returns to the client. If you clear the check box and click
	  "Generate UI on Server" a message box appears on the server computer and the
	  client is in a wait state until you attend to the message box. Usually, no
	  one is there to attend to the message box on the server, which leaves the
	  client in a wait state forever forcing them to shutdown the process to gain
	  control.
	
	  WARNING: You may not see the message box on the remote computer and may have
	  to use the Task Manager to stop the Foxserver.exe process. This causes an
	  error message to appear on the client which gives you back control of the
	  client. If you are running the COM server locally, the message box appears
	  behind the Visual FoxPro form. To switch to the message box, use ALT-TAB
	  until the Windows flag is selected. Once the message box is in focus, click
	  the OK button and the client operates normally.
	
	  The unattended mode gets around this problem by not allowing any UI in an out
	  of process (exe) COM server. The server raises the error number 2031
	  "User-interface operation not allowed at this time." The SYS(2335) function
	  has no effect on in-process servers (dll), because no UI is allowed to
	  display by default and this cannot be changed.
	
	3. Visual FoxPro 6.0 allows you to pass arrays to the COM Server. Select either
	  option button to pass the array by reference or by value and, then click the
	  pass array button. The pass array button uses the new COMArray() function and
	  sets up Visual FoxPro to pass the entire array either by reference or by
	  value. It also determines whether the COM object expects the array to be zero
	  or one based. The COMArray() setting is specific to a particular COM object
	  and is not a global setting. Below is code from the Click event of the Pass
	  Array button in the COMSample form. The sample uses the COMArray() function
	  to allow Visual FoxPro to pass the array by reference or by value:
	
	        IF Thisform.PageFrame1.Page3.OptionGroup1.Option1.Value = 1
	         =COMArray(Thisform.oFoxServer,11) && 1 based, passed by Reference.
	        ELSE
	         =COMArray(Thisform.oFoxServer,1)  && 1 based, passed by Value.
	        ENDIF
	
	In the sample, if you pass the array by reference, it calls the GetArray method
	in the COM server. The method then adds five (5) to each element of the array
	and then sums the entire array and passes back the total. Notice the value of
	the elements in the list box have changed because the array is passed by
	reference. If you pass the array by value, the server still adds five (5) to
	each element, but the array does not change back on the client.
	
	(c) Microsoft Corporation 1999, All Rights Reserved.
	Contributions by David Botzenhart, Microsoft Corporation
	
	
	REFERENCES
	==========
	
	For more information, please refer to the Dcomcnfg.hlp file.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbfile kbSample kbCOMt kbvfp600 kbGrpDSFox kbDSupport 
	Technology        : kbVFPsearch kbAudDeveloper kbVFP600
	Version           : :6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
