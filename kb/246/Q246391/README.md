---
layout: page
title: "Q246391: PaswordChangeFlags Set to 4 or Higher Causes Access Violation"
permalink: /kb/246/Q246391/
---

## Q246391: PaswordChangeFlags Set to 4 or Higher Causes Access Violation

{% raw %}

	Article: Q246391
	Product(s): Internet Information Server
	Version(s): winnt:4.0
	Operating System(s): 
	Keyword(s): kbWinNT400PreSP7Fix
	Last Modified: 08-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Internet Information Server version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If you set the PasswordChangeFlags value to 4 or higher, and the number of days
	that a user's password will expire is less than the PasswordExpirePrenotifyDays
	value, an Access Violation error message occurs.
	
	CAUSE
	=====
	
	If the PasswordChangeFlags value is set to 4 or higher, when IIS checks to see
	if it needs to redirect the client to the password expire page, the function IIS
	calls returns NULL instead of a pointer to a string containing the URL. IIS
	incorrectly attempts to use the pointer to check the string to see if it is
	empty without first checking to see if it has a valid pointer.
	
	RESOLUTION
	==========
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem described in this article and should be applied only to
	systems experiencing this specific problem.
	
	To resolve this problem, contact Microsoft Product Support Services to obtain the
	fix. For a complete list of Microsoft Product Support Services phone numbers and
	information on support costs, please go to the following address on the World
	Wide Web:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	NOTE: In special cases, charges that are normally incurred for support calls may
	be canceled, if a Microsoft Support Professional determines that a specific
	update will resolve your problem. Normal support costs will apply to additional
	support questions and issues that do not qualify for the specific update in
	question.
	
	The English version of this fix should have the following file attributes or
	later:
	
	  
	
	  Date         Time       Version   Size    File name     Platform
	  ----------------------------------------------------------------
	  11/15/1999   07:06:25pm 4.2.731.1 329,024 Asp.dll       x86
	  11/15/1999   07:04:36pm 4.2.731.1 184,736 Infocomm.dll  x86
	  11/15/1999   07:05:23pm 4.2.731.1 11,248  Iwrps.dll     x86
	  11/15/1999   07:05:33pm 4.2.731.1 38,256  Ssinc.dll     x86
	  11/15/1999   07:05:42pm 4.2.731.1 25,360  Sspifilt.dll  x86
	  11/15/1999   07:05:21pm 4.2.731.1 228,464 W3svc.dll     x86
	  11/15/1999   07:05:03pm 4.2.731.1 87,508  Wam.dll       x86
	
	  11/15/1999   07:05:45pm 4.2.731.1 549,648 Asp.dll       alpha
	  11/15/1999   07:04:02pm 4.2.731.1 303,888 Infocomm.dll  alpha
	  11/15/1999   07:04:47pm 4.2.731.1 16,656  Iwrps.dll     alpha
	  11/15/1999   07:04:58pm 4.2.731.1 60,176  Ssinc.dll     alpha
	  11/15/1999   07:05:05pm 4.2.731.1 39,696  Sspifilt.dll  alpha
	  11/15/1999   07:04:45pm 4.2.731.1 383,760 W3vc.dll      alpha
	  11/15/1999   07:04:29pm 4.2.731.1 149,264 Wam.dll       alpha
	
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Internet Information Server 4.0.
	
	MORE INFORMATION
	================
	
	
	
	Additional query words:
	
	======================================================================
	Keywords          : kbWinNT400PreSP7Fix 
	Technology        : kbiisSearch kbiis400
	Version           : winnt:4.0
	Hardware          : ALPHA x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
