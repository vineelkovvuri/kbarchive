---
layout: page
title: "Q168058: PRB: Application Wizard EXE or APP Gives Path or File Error"
permalink: /kb/168/Q168058/
---

## Q168058: PRB: Application Wizard EXE or APP Gives Path or File Error

{% raw %}

	Article: Q168058
	Product(s): Microsoft FoxPro
	Version(s): 5.0 5.0a
	Operating System(s): 
	Keyword(s): kbtool kbvfp kbvfp500 kbvfp500a
	Last Modified: 20-AUG-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 5.0, 5.0a 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If an EXE or APP built from a project created by the Application Wizard is run
	from a directory on a drive that does not contain the home directory of the
	application project and source files, one or more of the following errors will
	occur:
	
	  "Invalid path or file name"
	
	  -or-
	
	  "File "<path to app or exe>\<appname>.mpr" not found"
	
	CAUSE
	=====
	
	The application home directory is hard-coded into the project's main program,
	and the wzApplication.DoMenu method contains a check for the existence of the
	.MPR file, while the EXE or APP only contains the compiled MPX code.
	
	RESOLUTION
	==========
	
	Invalid Path or File name
	-------------------------
	
	1. To alleviate the "Invalid path or file name" error, open the main program in
	  the project created by the Application Wizard. The main program will have the
	  same name as the project name and is located in the "<application
	  directory name>\Progs" directory. It will also appear in bold in the
	  Project Manager's Code tab under the Programs heading. Replace the line:
	
	        CD "<path\directory containing app>"
	
	with the following:
	
	       * Are we running from a PRG (FXP)? If so, strip off all after the
	        * last 2 "\" characters else strip all after the last "\" character
	
	        CD (SUBSTR(SYS(16,0),1,RAT('\',SYS(16,0), ;
	          IIF(".FXP"$SYS(16,0),2,1))-1))
	
	1. In the WZApplication.DoMenu method located in the class library
	  \VFP\wizards\appwiz.vcx, the following code is used to verify the existence
	  and then call menus used within the application:
	
	        LPARAMETERS tcFileName
	        LOCAL lcFileName
	
	        lcFileName=ALLTRIM(tcFileName)
	        IF EMPTY(lcFileName)
	           RETURN .F.
	        ENDIF
	        lcFileName=LOWER(FULLPATH(lcFileName))
	        IF NOT "."$lcFileName
	           lcFileName=lcFileName+".mpr"
	        ENDIF
	        IF NOT FILE(lcFileName)
	           this.FileNotFoundMsgBox(lcFileName)
	           RETURN .F.
	        ENDIF
	        DO (lcFileName)
	
	File <path and mpr name> Not Found
	----------------------------------
	
	To alleviate the "File <path and mpr name> not found" error, change the
	line:
	
	     lcFileName=lcFileName+".mpr"
	
	to:
	
	     * Since the lowest level program is an FXP, we are not in an APP or EXE,
	     * so it is OK to look for MPR since we know source code is available.
	     * Otherwise look for MPX contained in APP or EXE
	
	     lcFileName = lcFileName+ iif(".FXP"$sys(16,0),".mpr", ".mpx")
	
	STATUS
	======
	
	Microsoft is researching this problem and will post new information here in the
	Microsoft Knowledge Base as it becomes available.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Behavior
	---------------------------
	
	1. Type the following commands in the Command Window within Visual FoxPro:
	
	       MD c:\awtest
	       CD c:\awtest
	
	2. Run the Application Wizard by selecting Tools/Wizards from the Visual FoxPro
	  system menu. Select All from the submenu, then Application Wizard from the
	  list and select OK.
	
	3. In step 1, Call the application "awtest" and select Complete Application.
	
	4. Select Finish.
	
	5. Build this project into an EXE file.
	
	6. Copy the EXE to a different directory than the one it was built in.
	
	7. Run the EXE.
	
	The steps in the RESOLUTION section above describe how to fix the main program in
	an application that has already been created. By the object- oriented nature of
	Visual FoxPro, the change in the DoMenu method will automatically be applied to
	future applications created with the Application Wizard. In order to fix the
	main program template so that future applications built with the Application
	Wizard will correctly resolve the default path, you must modify the template
	located in the Appwiz.dbf table. This can be done by completing the following
	steps:
	
	1. From the Command Window:
	
	        USE HOME()+'wizards\appwiz.dbf'
	        BROWSE FOR type = 'STARTUP PROGRAM'
	        MODIFY MEMO DATA1
	
	2. Locate the following line in the memo edit window:
	
	        *<CD>*
	
	3. Delete the above line, and replace it with:
	
	        CD (SUBSTR(SYS(16,0),1,RAT('\',SYS(16,0), ;
	          IIF(".FXP"$SYS(16,0),2,1))-1))
	
	4. Close the edit window, then type USE in the Command Window to close the
	  Appwiz table and save the changes.
	
	5. Future applications created with the Application Wizard will contain both the
	  changes in the main program and the DoMenu method, and neither of the errors
	  described in the SYMPTOMS section above will occur.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbtool kbvfp kbvfp500 kbvfp500a 
	Technology        : kbVFPsearch kbAudDeveloper kbVFP500 kbVFP500a
	Version           : 5.0 5.0a
	
	=============================================================================
	

{% endraw %}
