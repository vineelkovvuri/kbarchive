---
layout: page
title: "Q269615: SMS: Mixed Languages in SMS 2.0 Sites That Share a Domain"
permalink: /kb/269/Q269615/
---

## Q269615: SMS: Mixed Languages in SMS 2.0 Sites That Share a Domain

{% raw %}

	Article: Q269615
	Product(s): Microsoft Systems Management Server
	Version(s): winnt:2.0
	Operating System(s): 
	Keyword(s): kbsms200
	Last Modified: 28-OCT-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server version 2.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	When multiple Microsoft Systems Management Server (SMS) 2.0 sites share the same
	domain, and Microsoft Windows NT Logon Installation or Windows NT Logon
	Discovery is enabled, if the sites are installed with different languages, for
	example, U.S. English and French, the senior site updates the logon points. All
	subsequent client installations are written in the language of the senior site.
	This behavior is expected and occurs because the senior site maintains the logon
	points.
	
	MORE INFORMATION
	================
	
	In SMS, the International Client Pack (ICP) allows you to install clients with
	different languages within SMS, and maintain separate language components for
	multiple languages. When you install an ICP to all sites within a domain, it
	adds additional language support to the product. During installation, the ICP
	prompts the client components to perform a language evaluation based on the
	client's regional settings.
	
	ICPs are specific to each service pack revision. For example, the ICP for an SMS
	Service Pack 1 (SP1) site does not function correctly in an SMS Service Pack 2
	(SP2) site. In addition, components from all sites must be at the same software
	revision level for the ICP to function. Any "hot fixes" applied to one site must
	be applied to all sites.
	
	REFERENCES
	==========
	
	For additional information, click the article number below to view the article
	in the Microsoft Knowledge Base:
	
	  Q235726 Specifying Senior Site for Windows NT Logon Point Management
	
	  Q202941 Systems Management Server International Client Packs
	
	You can also learn more about ICPs (and SMS) by referring to the following
	sources:
	
	- The Microsoft BackOffice Resource Kit, Chapter 3, "Using SMS 2.0 in a
	  Multilingual Environment"
	
	- The ICP Release Notes for a specific ICP.
	
	Additional query words: prodsms
	
	======================================================================
	Keywords          : kbsms200 
	Component         : SystemManagement
	Technology        : kbSMSSearch kbSMS200
	Version           : winnt:2.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
