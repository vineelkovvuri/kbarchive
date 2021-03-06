---
layout: page
title: "Q185024: XCON: MTA NDRs with Loop Detection After Upgrading Bridgehead"
permalink: /kb/185/Q185024/
---

## Q185024: XCON: MTA NDRs with Loop Detection After Upgrading Bridgehead

{% raw %}

	Article: Q185024
	Product(s): Microsoft Exchange
	Version(s): winnt:5.0 SP2,5.5
	Operating System(s): 
	Keyword(s): 
	Last Modified: 22-OCT-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, versions 5.0 SP2, 5.5 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	After you upgrade a bridgehead to Exchange Server 5.0 Service Pack 2 or Exchange
	Server 5.5 and the rest of the site remains with an earlier version of Exchange
	Server, the message transfer agent (MTA) may generate a non-delivery report
	(NDR) with loop detection. The following NDR may be received by the client who
	sent the message:
	
	  From: System Administrator
	  Sent: Tuesday, April 14, 1998 1:25 PM
	  Subject: Undeliverable: Subject Line for Loop Detect
	  Your message did not reach some or all of the intended recipients.
	  Subject: FW: Monday attendance
	  Sent: 04/14/1998 1:25:26 PM
	  The following recipient(s) could not be reached:
	  USER, Test on 04/14/1998 1:25:28 PM
	  The recipient was detected looping within the message transfer service.
	
	CAUSE
	=====
	
	This problem has specific conditions under which the NDR can occur. The problem
	occurs when a user sends mail to another user on the same server and uses the
	MSMail Proxy or SMTP Proxy of the user. The proxy address can be selected from
	the personal address book, or typed in as a one-off address. If the user selects
	the recipient from the Global Address List, the NDR does not occur. Also, this
	only occurs when the sender is using the Exchange 4.0 client. This does not
	occur when the sender is running the Exchange 5.0 client, Outlook 97, or Outlook
	98. The final condition that must be met is that the bridgeheads are a later
	version of Exchange Server than the user servers. For example, if all of the
	computers running Exchange Server in the site are using version 5.0 Service Pack
	1, this problem does not occur. When the bridgehead is upgraded to Exchange
	Server 5.0 Service Pack 2, or to Exchange Server 5.5, the NDR may appear.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Exchange Server version 5.0
	Service Pack 2.
	
	
	A supported fix is now available, but has not been fully regression-tested and
	should be applied only to systems experiencing this specific problem. Unless you
	are severely impacted by this specific problem, Microsoft recommends that you
	wait for the next Service Pack that contains this fix. Contact Microsoft
	Technical Support for more information.
	
	
	Microsoft has confirmed this to be a problem in Exchange Server version 5.5. This
	problem has been corrected in the latest U.S. Service Pack for Microsoft
	Exchange Server version 5.5. For information about obtaining the Service Pack,
	query on the following word in the Microsoft Knowledge Base (without the
	spaces):
	
	  S E R V P A C K
	
	Additional query words: XADM XCON Loop 290 NDR route routing upgrade bridgehead
	
	======================================================================
	Keywords          :  
	Technology        : kbExchangeSearch kbExchange550 kbZNotKeyword2 kbExchange500SP2
	Version           : winnt:5.0 SP2,5.5
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
