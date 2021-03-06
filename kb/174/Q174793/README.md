---
layout: page
title: "Q174793: SMS: SETLS Domain Enumeration Using Smsls.ini and Win.ini"
permalink: /kb/174/Q174793/
---

## Q174793: SMS: SETLS Domain Enumeration Using Smsls.ini and Win.ini

{% raw %}

	Article: Q174793
	Product(s): Microsoft Systems Management Server
	Version(s): winnt:1.2
	Operating System(s): 
	Keyword(s): kbusage kbInventory smsinv
	Last Modified: 25-JUL-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server version 1.2 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If you specify domain:sitecode in the [SMS] section of the Win.ini file, SETLS
	always enumerates the domain. That is, SETLS does not select a Systems
	Management Server logon server from the [Servers] section of the client's
	Sms.ini file. This results in a longer delay during the initial logon.
	
	CAUSE
	=====
	
	SETLS enumerates the domain when there is a mismatch between the KeyMatch value
	set in the [SMSLSIni] section of the client's Sms.ini file and the current
	value.
	
	For example, suppose the following is the [SMS] section from a client's Win.ini
	file:
	
	     [SMS]
	     domain=VIPER_X:Q45
	
	The following is the [SMSLSIni] section of the client's Sms.ini file:
	
	     [SMSLSIni]
	     ValidatingServer=\\Servername
	     FileName=Z:\smsls.ini
	     FileTime=31fa4fc0
	     SectionMatch=WIN.INI
	     KeyMatch=VIPER_X
	     Domain=VIPER_X
	
	Note that the domain name under the [SMS] section is VIPER_X:Q45 and the KeyMatch
	value under the [SMSLSIni] section is VIPER_X. SETLS enumerates the VIPER_X
	domain as long as those two values are different.
	
	WORKAROUND
	==========
	
	To work around this problem, manually modify the [SMSLSIni] section and change
	the KeyMatch value to equal the same value set for the domain entry under the
	[SMS] section in the client's Win.ini file.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Systems Management Server
	version 1.2. This problem was corrected in the latest Microsoft Systems
	Management Server 1.2 U.S. Service Pack. For information on obtaining the
	service pack, query on the following word in the Microsoft Knowledge Base
	(without the spaces):
	
	  S E R V P A C K
	
	MORE INFORMATION
	================
	
	As long as the values in the [SMSLSIni] section of the client's Sms.ini file
	match the current values, SETLS should select a Systems Management Server logon
	server from the [Servers] section of that file, and should not enumerate the
	domain.
	
	NOTE: The behavior of Setls has changed in SMS SP4. For additional information
	about this, click the article number below to view the article in the Microsoft
	Knowledge Base:
	
	  Q187369 SMS: SETLS Stores File Time of Win.ini File
	
	Additional query words: prodsms smsls.ini
	
	======================================================================
	Keywords          : kbusage kbInventory smsinv 
	Technology        : kbSMSSearch kbSMS120
	Version           : winnt:1.2
	Issue type        : kbbug
	
	=============================================================================
	

{% endraw %}
