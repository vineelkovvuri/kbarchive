---
layout: page
title: "Q281683: XADM: &quot;A Fatal Error (0x8004011d) Occurred&quot; Event ID 11"
permalink: /kb/281/Q281683/
---

## Q281683: XADM: &quot;A Fatal Error (0x8004011d) Occurred&quot; Event ID 11

{% raw %}

	Article: Q281683
	Product(s): Microsoft Exchange
	Version(s): 5.5
	Operating System(s): 
	Keyword(s): kberrmsg
	Last Modified: 05-JUN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 5.5 
	- Microsoft Exchange 2000 Server 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	In a mixed Microsoft Exchange 2000 Server and Microsoft Exchange Server 5.5
	environment, the following event ID message may logged in the Application log by
	the Microsoft Exchange Event service on the Exchange Server 5.5 computer:
	
	  Event ID: 11
	  Source: MSExchangeES
	  Type: Error
	  Category: General
	  Description:
	  A fatal error (0x8004011d) occurred in an IExchangeEventSink while processing
	  message [Subject = "test message"].
	
	This event occurs after an Exchange 2000 user modifies an event script on an
	Exchange Server 5.5 public folder. If an Exchange Server 5.5 user modifies the
	same script, the script functions correctly.
	
	MORE INFORMATION
	================
	
	The value 8004011d from the Description box of this event ID message maps to the
	MAPI error MAPI_E_FAILONEPROVIDER. This error code indicates that the provider
	could not log on. However, this is not a fatal error. In this scenario, the
	credentials are not correct and the user is not prompted with a dialog box
	because this error runs in the context of a service instead of interactively.
	
	When the Event service is triggered to run the event script, the Event service
	tries to impersonate the user who most recently modified that event script. When
	an Exchange 2000 user has been the most recent to modify the script, the Event
	service tries to log on as that user. However, because the Exchange Server 5.5
	service account does not have access rights to the Exchange 2000 user's mailbox
	the log on attempt is denied. The script cannot run and the event ID message
	indicated in the "Summary" section is logged.
	
	In Exchange Server 5.5 the service account has inherited permissions to every
	mailbox. Therefore, when an Exchange Server 5.5 user is the last user to modify
	the event script, the Event service has the correct permissions with which to
	log on in that user's context. However, in Exchange 2000, there is no service
	account that has permissions to all mailboxes.
	
	To resolve this behavior, grant the Exchange Server 5.5 service account rights to
	the user who is modifying the scripts. This permits the Event service the
	ability to log on as the Exchange 2000 user to run the script.
	
	Additional query words: exch2kp2w 0x8004011d user modifies script
	
	======================================================================
	Keywords          : kberrmsg 
	Technology        : kbExchangeSearch kbExchange550 kbZNotKeyword2 kbExchange2000Search kbExchange2000Serv
	Version           : :5.5
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
