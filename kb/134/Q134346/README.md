---
layout: page
title: "Q134346: Remoteboot Workstation Cannot Reconnect After Net 808 Errors"
permalink: /kb/134/Q134346/
---

## Q134346: Remoteboot Workstation Cannot Reconnect After Net 808 Errors

{% raw %}

	Article: Q134346
	Product(s): Microsoft Windows NT
	Version(s): 2.2c,3.5
	Operating System(s): 
	Keyword(s): 
	Last Modified: 04-FEB-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 3.5 
	- Microsoft LAN Manager, version 2.2c 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	If you are using a diskless remoteboot workstation you cannot regain access to
	your drive C after the following network error appears:
	
	  Net 808: Incorrect response from network
	
	This symptom occurs if the following conditions apply:
	
	- Your workstation boots from a Windows NT 3.5 remoteboot server.
	
	- Your workstation is running LAN Manager for MS-DOS, version 2.2c.
	
	- Your workstation has at least one network connection to your remoteboot
	  server in addition to the drive C connection.
	
	- Your remoteboot server has the AutoDisconnect parameter set to a value of
	  greater than zero.
	
	- Your server's AutoDisconnect timer expired for your drive C connection.
	
	CAUSE
	=====
	
	There are two causes:
	
	- Your remoteboot server incorrectly auto-disconnects your drive C without
	  disconnecting your other network connection to the remoteboot server.
	
	- When you attempt to reconnect to your drive C, your workstation uses your
	  computer remoteboot startup credentials (the computer name), instead of your
	  logon name and password credentials.
	
	RESOLUTION
	==========
	
	To resolve this problem, upgrade to Windows NT version 3.51 or obtain the fix
	mentioned below.
	
	To work around this problem:
	
	- Set AutoDisconnect to a greater value on the remoteboot server. However, this
	  only reduces the frequency of the problem; it does not eliminate it. To
	  change the AutoDisconnect time value, type:
	
	  net config server /autodisconnect:<time>
	
	  where <time> is a number in the range of -1 to -65535 minutes. The
	  default value for AutoDisconnect is 15, not -1 as stated in Help.
	
	  -or-
	
	- Set AutoDisconnect to -1 to never disconnect. This may not be a feasible
	  option depending on how many remoteboot workstations you have per server.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT version 3.5. A fix to
	this problem is in development, but has not been regression-tested and may be
	destabilizing in production environments. Microsoft does not recommend
	implementing this fix at this time. Contact Microsoft Product Support Services
	for more information on the availability of this fix.
	
	
	MORE INFORMATION
	================
	
	A diskless workstation can have two sets of credentials for connections to the
	remoteboot Windows NT server.
	
	When your workstation boots, it establishes a connection to the remoteboot server
	using the workstation name as its user ID to get permission for downloading its
	network software. This connection becomes your drive C.
	
	After booting, you log on using the second set of credentials, that is your user
	name and password, and establish connections using these credentials to shared
	directories on the remoteboot server (with the Net Use command, etc.). For
	example, you may connect drive H to your home directory located on the
	remoteboot server.
	
	If the remoteboot server has an AutoDisconnect setting of 15 minutes and your
	workstation maintains network activity on drive H, but generates no network
	traffic for 15 minutes on the remoteboot connection to your drive C, the server
	disconnects drive C, but leaves drive H connected. As a result you get the
	unrecoverable Net 808 error mentioned above when your workstation attempts to
	access its disconnected drive C.
	
	Additional query words: 2.20 rpl ripl
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNT350search kbWinNTSsearch kbWinNTS350 kbWinNTS350search kbAudDeveloper kbLanManSearch kbLanMan220c
	Version           : :2.2c,3.5
	
	=============================================================================
	

{% endraw %}
