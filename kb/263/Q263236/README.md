---
layout: page
title: "Q263236: XWEB: Exchange Server 5.5 Outlook Web Access Logon Process"
permalink: /kb/263/Q263236/
---

## Q263236: XWEB: Exchange Server 5.5 Outlook Web Access Logon Process

{% raw %}

	Article: Q263236
	Product(s): Microsoft Exchange
	Version(s): WINDOWS:5.5
	Operating System(s): 
	Keyword(s): 
	Last Modified: 06-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Outlook Web Access, version 5.5 Service Packs 1, 2, 3 
	- Microsoft Exchange Server, version 5.5 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The article is a resource to help administrators better understand what occurs
	when a user uses Outlook Web Access (OWA) to gain access to Microsoft Exchange
	Server version 5.5. This article provides an overview of the process and does
	not necessarily cover all of the steps that are required to gain access to
	Exchange Server by using Outlook Web Access.
	
	MORE INFORMATION
	================
	
	When a user uses Outlook Web Access to gain access to Microsoft Exchange Server
	version 5.5:
	
	- The user makes a Hypertext Transfer Protocol (HTTP) request for the Exchange
	  Server virtual directory on an Internet Information Service (IIS) server (for
	  example, http://<server_name>/exchange).
	
	- Because this is a request for an application, IIS automatically processes the
	  Global.asa file. This file contains scripts to initialize application and
	  session variables, load the path to the
	  HKEY_LOCAL_USER\System\CurrentControlSet\Services\MSExchangeWeb registry key,
	  and initialize objects that are used throughout the application.
	
	- An Internet Server Application Programming Interface (ISAPI) filter
	  (ExchFilt.dll) that examines all incoming Uniform Resource Locators (URLs)
	  handles localization. If the filter detects a URL for one of the applications
	  that are defined in the
	  HKEY_LOCAL_USER\System\CurrentControlSet\Services\MSExchangeWeb\Applications
	  key (Exchange Server is defined by default, but you can add any application
	  to this list), the filter performs the following tasks:
	
	   - Examines the AcceptLanguage header from the browser. (The AcceptLanguage
	     header specifies the language that a given browser prefers.)
	
	   - Looks up the header by using the table in the
	     HKEY_LOCAL_USER\System\CurrentControlSet\Services\MSExchangeWeb\AcceptLanguages
	     key.
	
	   - Inserts the directory name in the URL following the application name. For
	     example, if you have a browser that prefers USA-English, the following
	
	  //<my_server>/exchange/logon.asp
	
	     becomes
	
	  //<my_server>/exchange/usa/logon.asp
	
	- The default document for the Exchange Server virtual directory (Default.htm)
	  is sent to the browser. This file performs a simple redirect to
	  URL=/exchange/logon.asp
	
	- Logon.asp performs the following tasks:
	
	   - Active Server Pages (ASP) files can contain a combination of server and
	     client scripts. The ASP component in IIS performs server operations and
	     also sends generated Hypertext Markup Language (HTML) pages to the Web
	     browser. This is how the initial logon window is built and displayed.
	
	   - A server operation obtains the browser type and version to determine if
	     the browser that made the request is supported. If the browser is not
	     supported, Logon.asp indicates that the browser is not supported and
	     nothing more is done.
	
	For additional information about client requirements, click the article number
	below to view the article in the Microsoft Knowledge Base:
	
	  Q239569 XWEB: Requirements for Outlook Web Access
	
	   - Logon.asp prompts the user to either provide a mailbox name or to choose
	     anonymous access. Annonymous access allows the user to read from and post
	     to public folders anonymously and also to find names in an address book by
	     using Lightweight Directory Access Protocol (LDAP).
	
	   - Logon.asp submits an HTML form that contains a mailbox value (the mailbox
	     is blank if the user chooses anonymous access).
	
	   - The action that is associated with this HTML form is to call Logonfrm.asp.
	
	- Logonfrm.asp performs the following tasks:
	
	   - If the user provided a mailbox at the logon window and OWA has not already
	     gained access to that mailbox in this session, Logonfrm.asp returns a
	     Response.Status of "401 Unauthorized" to force authentication.
	
	   - Logonfrm.asp creates a Messaging Application Programming Interface (MAPI)
	     session by using the Collaboration Data Objects (CDO) logon method. This
	     MAPI session provides OWA with an interface to the Exchange Server
	     computer.
	
	For additional information about using this logon method, click the article
	number below to view the article in the Microsoft Knowledge Base:
	
	  Q195662 HOWTO: Log On to Exchange with the ProfileInfo Parameter
	
	   - Logonfrm.asp passes control to Root.asp along with an indication of the
	     type of access that the user requested (authenticated or anonymous).
	
	- Root.asp is the last step in the logon process, and Root.asp performs the
	  following tasks:
	
	   - Root.asp determines which information store to open (either a private
	     mailbox or the public folder tree).
	
	   - If the authenticated user's password is set to expire in fewer days than
	     the iNotificationPeriod value (14 days by default), Root.asp alerts the
	     user.
	
	For additional information, click the article number below to view the article in
	the Microsoft Knowledge Base:
	
	  Q190433 XWEB: Err Msg: Current Password Is About to Expire in 0 Days
	
	   - Root.asp sets up the main Outlook Web Access interface, which includes the
	     navigation bar and folder list.
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbOutlookSearch kbExchangeSearch kbExchange550 kbZNotKeyword2 kbOWASearch kbOWA550SP1 kbOWA550SP2 kbOWA550SP3
	Version           : WINDOWS:5.5
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
