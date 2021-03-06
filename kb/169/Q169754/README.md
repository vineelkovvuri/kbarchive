---
layout: page
title: "Q169754: XADM: How to Set Up Batch Auto-Forward Rules Using Exchange"
permalink: /kb/169/Q169754/
---

## Q169754: XADM: How to Set Up Batch Auto-Forward Rules Using Exchange

{% raw %}

	Article: Q169754
	Product(s): Microsoft Exchange
	Version(s): winnt:5.0,5.5
	Operating System(s): 
	Keyword(s): kbusage exc5 exc55
	Last Modified: 11-JUN-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, versions 5.0, 5.5 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article explains how to use a directory import\directory export file (.csv
	file) to configure all mailboxes with Alternate Recipients instead of manually
	configuring each mailbox separately.
	
	MORE INFORMATION
	================
	
	The following steps present a method to adds alternate recipient to mailboxes
	using the .csv files.
	
	1. Export the recipients (mailboxes) to a .csv file.
	
	2. Edit the .csv file and insert a column named "Alternate Recipient." Beneath
	  the "Alternate Recipient" field, insert the Distinguished Name (DN) of the
	  recipient that the mail will be forwarded to.
	
	3. If you would like to use the "Deliver to Both" option, you can insert a new
	  column named "Deliver to both". If you want the messages to be delivered to
	  both mailboxes of the original and the "Alternate Recipient", type the number
	  1 in this new field; otherwise type a 0.
	
	4. Save this file in .csv formats and close it.
	
	5. Import this .csv file into the Exchange Server. If you receive an error when
	  importing the .csv file to Exchange Server, see the Microsoft Knowledge Base
	  article referenced below in the "More Information" section.
	
	6. Confirm that the recipients who were specified as the "Alternate Recipients"
	  actually received the messages that were addressed to the original mailbox.
	
	The following is a sample comma-delimited header of the .csv file used in this
	process to setup these Delivery Options:
	
	     Obj-Class,Mode,Directory Name,Alternate Recipient,Deliver to both,
	     Mailbox,modify,Admin,/o=Microsoft/ou=HARLEM/cn=Recipients/cn=SueW,1,
	     Mailbox,modify,Beth,/o=Microsoft/ou=HARLEM/cn=Recipients/cneT,0,
	
	NOTE: The Exchange Server Administrator program provides a method that manually
	adds alternate recipient to a mailbox. This manual method has to be done to
	every mailbox individually. It uses the Delivery Options tab of the mailbox's
	property pages to modify the mailbox and select the Alternate recipient.
	
	If you receive an error message when importing the .csv file to Exchange Server
	(step 5 above), see the following article.
	
	For additional information, please see the following article in the Microsoft
	Knowledge Base:
	
	  Q155743 XADM: Directory Import Error: Unable to Process Object
	
	Additional query words: bulk export
	
	======================================================================
	Keywords          : kbusage exc5 exc55 
	Technology        : kbExchangeSearch kbExchange500 kbExchange550 kbZNotKeyword2
	Version           : winnt:5.0,5.5
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
