---
layout: page
title: "Q242215: IAS RADIUS Realms/Prefixes Do Not Work Per Design Specifications"
permalink: /kb/242/Q242215/
---

## Q242215: IAS RADIUS Realms/Prefixes Do Not Work Per Design Specifications

{% raw %}

	Article: Q242215
	Product(s): Microsoft Windows NT
	Version(s): 
	Operating System(s): 
	Keyword(s): 
	Last Modified: 06-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT version 4.0 Option Pack 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Remote Authentication Dial-In User Service (RADIUS) realms and prefixes do not
	work as per the original design specification.
	
	For example, define a RADIUS realm named "<realmname>" with an "m/" prefix
	that grants users logon access only to the mail service. When a dial-up user
	logs on to the Internet service provider (ISP) as "m/<username>", RADIUS
	sees the "m/" prefix and applies the RADIUS profile, which restricts the user
	account to accessing mail only. The "m/<username>" logon information is
	then forwarded to the Microsoft Commercial Internet System (MCIS) Membership
	server and the user is logged on with the appropriate restrictions.
	
	If, however, the user logs on with an "M/" prefix, the RADIUS server does not
	apply the "m/" profile because the RADIUS server is case sensitive for realms
	and prefixes. The RADIUS server also forwards "M/<username>" to the MCIS
	Membership server, and the user is successfully logged on without the necessary
	restrictions. The Membership server successfully authenticates the user because
	it is case insensitive for prefixes and realms.
	
	Therefore, if a user types a realm and prefix in a different case than was
	originally defined, the user bypasses the restrictions defined in the profile on
	the RADIUS server. ISPs have no way to limit user access to the services that
	they are providing to their users.
	
	RESOLUTION
	==========
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem that is described in this article. Only apply it to systems
	that are experiencing this specific problem. This fix may receive additional
	testing. Therefore, if you are not severely affected by this problem, Microsoft
	recommends that you wait for the next Windows NT 4.0 service pack that contains
	this fix.
	
	To resolve this problem immediately, contact Microsoft Product Support Services
	to obtain the fix. For a complete list of Microsoft Product Support Services
	phone numbers and information about support costs, visit the following Microsoft
	Web site:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	NOTE: In special cases, charges that are ordinarily incurred for support calls
	may be canceled if a Microsoft Support Professional determines that a specific
	update will resolve your problem. The usual support costs will apply to
	additional support questions and issues that do not qualify for the specific
	update in question.
	
	The English-language version of this fix should have the following file
	attributes or later:
	
	  Date      Time                 Size    File name     Platform
	  -------------------------------------------------------------
	  9/3/99    8:48am              231,680  Authsrv.exe   x86
	  9/3/99    8:49am              347,408  Authsrv.exe   Alpha
	
	
	
	STATUS
	======
	
	Microsoft has confirmed that this is a problem in Microsoft Windows NT 4.0.
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNT400search kbWinNT400OptionPack
	Version           : :
	Hardware          : ALPHA x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
