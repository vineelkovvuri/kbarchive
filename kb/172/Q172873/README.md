---
layout: page
title: "Q172873: SMSINST: Messages Not Translated Into Correct Language"
permalink: /kb/172/Q172873/
---

## Q172873: SMSINST: Messages Not Translated Into Correct Language

{% raw %}

	Article: Q172873
	Product(s): Microsoft Systems Management Server
	Version(s): WINDOWS:1.0
	Operating System(s): 
	Keyword(s): kbenv kbsetup smsinst
	Last Modified: 17-DEC-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server Installer version 1.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If you have selected multiple languages during Systems Management Server
	Installer Setup, installation error messages are displayed in French rather than
	the locale specified. The languages affected include Danish, Dutch, Finnish,
	Norwegian, Portuguese, and Swedish.
	
	German, Spanish, Italian, English, and French have correctly translated messages.
	
	WORKAROUND
	==========
	
	To work around this problem, use the following procedure to manually edit
	Installer messages for the affected languages:
	
	1. On the Edit menu, click Installer Messages.
	
	2. From the Language Name list box, select the appropriate language.
	
	3. In the Messages list, select the first message. Note that the corresponding
	  message text appears to the right.
	
	4. Edit the Message Text field to reflect the correct translation for the
	  specified language.
	
	5. Repeat step 4 for each message.
	
	After you complete this procedure, this information is saved in the Smsinstl.ini
	file located in the Windows or Winnt directory. You should save the appropriate
	sections as a template so that you do not need to repeat this procedure if
	Systems Management Server Installer is reinstalled or installed on additional
	reference computers. To save it as a template, perform the following steps:
	
	1. Locate the Smsinstl.ini file in the %SYSTEMROOT% directory (that is, the
	  Winnt directory on computers running Windows NT Systems or the Windows
	  directory on computers running Windows 95 or Windows 3.x).
	
	2. Back up the Smsinstl.ini file to a safe place.
	
	3. Open the backup version of the file in a text editor such as Notepad.
	
	4. Note the sections labeled [Languagex]. Each section contains the Installer
	  messages for that specific locale.
	
	5. If the Installer is installed again, the sections for the affected languages
	  could be cut from this backup and pasted into the new Smsinst.ini file.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Systems Management Server
	Installer 1.0. We are researching this problem and will post new information
	here in the Microsoft Knowledge Base as it becomes available.
	
	
	Additional query words: prodsms smsinst multiple
	
	======================================================================
	Keywords          : kbenv kbsetup smsinst 
	Technology        : kbSMSSearch kbSMSI100
	Version           : WINDOWS:1.0
	Issue type        : kbbug
	
	=============================================================================
	

{% endraw %}
