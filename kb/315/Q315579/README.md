---
layout: page
title: "Q315579: &quot;HTTP Error 403&quot;Err Msg When Password Changed w/OWA or Iisadmpwd"
permalink: /kb/315/Q315579/
---

## Q315579: &quot;HTTP Error 403&quot;Err Msg When Password Changed w/OWA or Iisadmpwd

{% raw %}

	Article: Q315579
	Product(s): Internet Information Server
	Version(s): 4.0,5.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 29-JAN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Internet Information Server version 4.0 
	- Microsoft Internet Information Services version 5.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you attempt to change a password in Outlook Web Access (OWA) or browse one
	of the .htr files directly, or if you try to execute a Common Gateway Interface
	(CGI), Internet Server Application Programming Interface (ISAPI), or other
	executable program from a directory that does not allow programs to be executed,
	you may receive the following error message in the Web browser:
	
	  HTTP Error 403
	
	  403.1 Forbidden: Execute Access Forbidden
	
	CAUSE
	=====
	
	The Iisadmpwd virtual directory in the Internet Service Manager does not have
	script permissions.
	
	RESOLUTION
	==========
	
	To resolve this problem, follow these steps:
	
	1. Open the Internet Service Manager Microsoft Management Console (MMC).
	
	2. Right-click the Iisadmpwd virtual directory and then click Properties.
	
	3. On the Virtual Directory tab, change the permissions from none to script.
	
	NOTE: By default, IISADMPWD is installed as a physical folder under Microsoft
	Windows 2000, but not as a virtual directory under Internet Information Services
	(IIS) version 5.0. Because of this, IIS does not recognize that the directory
	exists. For additional information, click the article number below to view the
	article in the Microsoft Knowledge Base:
	
	  Q268419 HOWTO: Enable Password Change Functionality for OWA
	
	If the problem persists, contact the administrator of the Web server.
	
	MORE INFORMATION
	================
	
	IIS 4.0 includes the capability that allows a Microsoft Windows NT 4.0 user to
	change passwords and to receive notification when a password is about to expire.
	IIS installs this functionality in the IISADMPWD virtual directory of the
	default Web site. This feature is implemented as a set of .htr files that are
	located in the %system%\System32\Inetsrv\Iisadmpwd directory and the ISAPI
	Ism.dll extension file.
	
	For more information about how to configure IIS to support password changes, view
	the "Notifying Clients of Password Status" topic in the Windows NT 4.0 Option
	Pack documentation.
	
	For more information, see the following Knowledge Base article:
	
	  Q184058 Unable to Change Password Using the IIS 4.0 Change Password Feature
	
	Additional query words: IIS4 IIS5 HTR
	
	======================================================================
	Keywords          :  
	Technology        : kbiisSearch kbiis500 kbiis400
	Version           : :4.0,5.0
	Issue type        : kbprb
	Solution Type     : kbpending
	
	=============================================================================
	

{% endraw %}
