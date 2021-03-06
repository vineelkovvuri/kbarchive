---
layout: page
title: "Q179932: Encarta: Amount from Contribution Is Incorrect"
permalink: /kb/179/Q179932/
---

## Q179932: Encarta: Amount from Contribution Is Incorrect

{% raw %}

	Article: Q179932
	Product(s): Microsoft Home Multimedia Titles
	Version(s): MACINTOSH:; WINDOWS:; :
	Operating System(s): 
	Keyword(s): kbtool kbimu
	Last Modified: 27-OCT-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Encarta 98 Encyclopedia for Windows 
	- Microsoft Encarta 98 Encyclopedia for Macintosh 
	- Microsoft Encarta Encyclopedia 99 
	- Microsoft Encarta Encyclopedia 2000 
	- Microsoft Encarta Encyclopedia Deluxe 2001 for Windows 
	- Microsoft Encarta Encyclopedia Standard 2001 for Windows 
	- Microsoft Encarta Reference Suite 99 
	- Microsoft Encarta Reference Suite 2000 
	- Microsoft Encarta Reference Suite 2001 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you use the Compound Interest InterActivity in Microsoft Encarta
	Encyclopedia to determine the amount of time you need to save $1 million, the
	dollar amount you type in the Monthly Contribution box multiplied by the number
	of years the InterActivity calculates you need to save may not match the Amount
	From Contribution calculated by the InterActivity.
	
	CAUSE
	=====
	
	This behavior can occur because the InterActivity rounds up the number of years
	you need to save to the nearest whole year. For example, if you need to save for
	44 years and 2 months, the InterActivity calculates you need to save for 45
	years to save $1 million.
	
	MORE INFORMATION
	================
	
	The Amount From Contribution calculated by the InterActivity is equal to the
	dollar amount you type in the Monthly Contribution box multiplied by the actual
	number of months you need to save $1 million. If the number of months is equal
	to a whole number of years, the discrepancy described in the Symptoms section
	does not occur.
	
	NOTE: Encarta Encyclopedia calculates the amount of time in full years. No months
	are displayed in the results.
	
	Additional query words: multi multi-media media mm deposit savings earning
	
	======================================================================
	Keywords          : kbtool kbimu 
	Technology        : kbHWMAC kbOSMAC kbHomeProdSearch kbHomeMMsearch kbEncartaSearch kbEncartaEncycSearch kbEncartaEnCyc2000 kbEncartaEnCyc1999 kbEncartaEnCyc1998Mac kbEncartaEnCyc1998 kbEncartaReference99 kbEncartaReference2000 kbEncartaReference2001
	Version           : MACINTOSH:; WINDOWS:; :
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
