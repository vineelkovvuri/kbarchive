---
layout: page
title: "Q243885: XFOR: Overview of the Exchange Application Converter for Notes"
permalink: /kb/243/Q243885/
---

## Q243885: XFOR: Overview of the Exchange Application Converter for Notes

{% raw %}

	Article: Q243885
	Product(s): Microsoft Exchange
	Version(s): 5.5
	Operating System(s): 
	Keyword(s): exc55
	Last Modified: 23-JAN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 5.5 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The Microsoft Exchange Application Converter for Lotus Notes is comprised of the
	Connection Manager for administrators and the Application Converter for
	developers.
	
	Replication requirements and the type of application being converted determine
	which program to use. Use the Connection Manager to move data in production
	environments or on an ongoing basis, and for simple Notes applications, such as
	discussions, as well as the Notes template-based applications: Customer
	Tracking, Status Reports, News, and Document Libraries. For more complex Notes
	applications where customizing is often required, you must use the Application
	Converter. You can also use the Application Converter when conversion does not
	require periodic synchronization.
	
	MORE INFORMATION
	================
	
	Connection Manager for Administrators
	-------------------------------------
	
	With this Microsoft Management Console (MMC) snap-in, administrators can create
	and manage connections, and migrate standard Notes applications.
	
	Replication Service
	The Connection Manager includes a Replication Service that automatically migrates
	Notes data to Exchange Server public folders or personal folders. This is a
	Windows NT service.
	
	Application Converter for Developers
	------------------------------------
	
	The Application Converter enables developers to:
	
	- Establish connections. Connections are pairings of Notes databases with
	  Exchange Server personal folders or public folders for transferring data.
	
	- Automatically convert Notes application designs to Outlook forms and views.
	
	- Develop custom Outlook forms with the included ActiveX controls customized so
	  that Outlook can duplicate Notes functionality. The controls are Radio Button
	  List, Checkbox List, Keyword List, Image, and Frame.
	
	- Perform a test or one-time migration of data from Notes to Exchange Server.
	
	- Export the connections and the application information to a file for import
	  by an administrator.
	
	The Exchange Application Converter for Lotus Notes does not support Notes version
	5. Application support for Notes 5 is currently being reviewed, and may be
	released in a future product.
	
	Additional query words: domino r5 client
	
	======================================================================
	Keywords          : exc55 
	Technology        : kbExchangeSearch kbExchange550 kbZNotKeyword2
	Version           : :5.5
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
