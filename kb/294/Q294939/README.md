---
layout: page
title: "Q294939: &quot;No More Local Devices&quot; Error Message When You Advertise"
permalink: /kb/294/Q294939/
---

## Q294939: &quot;No More Local Devices&quot; Error Message When You Advertise

{% raw %}

	Article: Q294939
	Product(s): Microsoft Systems Management Server
	Version(s): 2.0 SP2,2.0 SP3
	Operating System(s): 
	Keyword(s): kbenv kberrmsg kbtool kbsms200 kbsms200bug kbsms200fix kbAdvertisement kbPackage kbSoft
	Last Modified: 11-JUN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server versions 2.0 SP2, 2.0 SP3 
	-------------------------------------------------------------------------------
	
	IMPORTANT: This article contains information about modifying the registry. Before you modify the registry, make sure to back it up and make sure that you understand how to restore the registry if a problem occurs. For information about how to back up, restore, and edit the registry, click the following article number to view the article in the Microsoft Knowledge Base:
	
	  Q256986 Description of the Microsoft Windows Registry
	
	SYMPTOMS
	========
	
	Microsoft Windows 2000-based clients with the Systems Management Server (SMS)
	version 2.0 client installed can experience software distribution failures if
	the programs that are being run by the clients have the drive mode setting
	configured to "Requires drive letter" or "Requires specific drive letter".
	
	CAUSE
	=====
	
	This problem can occur when the SMS Advertised Programs Manager (Smsapm32.exe)
	on the client does not properly release the drives that are mapped to the SMS
	distribution point. When enough of the mapped network drives accumulate on the
	client, further attempts to create additional drives do not work. This results
	in the client being unable to run any more advertised programs.
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for Systems Management
	Server version 2.0. For additional information, please see the following article
	in the Microsoft Knowledge Base:
	
	  Q288239 SMS: How to Obtain the Latest Systems Management Server 2.0 Service
	  Pack
	
	
	
	WORKAROUND
	==========
	
	To avoid this problem, configure the drive mode setting on programs to use "Runs
	with UNC name".
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products that are
	listed at the beginning of this article. This problem was first corrected in
	Systems Management Server 2.0 Service Pack 4.
	
	MORE INFORMATION
	================
	
	WARNING: If you use Registry Editor incorrectly, you may cause serious problems
	that may require you to reinstall your operating system. Microsoft cannot
	guarantee that you can solve problems that result from using Registry Editor
	incorrectly. Use Registry Editor at your own risk.
	
	When this problem occurs on a client, evidence of the problem can be found in the
	Smsapm32.log file. The following example is an example of the log entries that
	are related to this problem.
	
	When the Program Is Configured with Requires Drive Letter
	---------------------------------------------------------
	
	  SCHED DATA : Return code = 0x800704e0; No more local devices.~~; Could not
	  enable program execution "navsms.cmd".~
	  SCHED DATA : Return code = 0x800704e0; No more local devices.~~;
	  IsExecutePossible returned error -2147023648 for program 'navsms.cmd'~
	
	When the Program Is Configured with Requires Specific Drive Letter
	------------------------------------------------------------------
	
	  SCHED DATA : Return code = 0x800704b1; The device is not currently connected
	  but it is a remembered connection.~~; Could not enable program execution
	
	If you examine the HKEY_USERS\.Default\Network registry key on the client, you
	may note the mapped network drives that are not being released.
	
	Recovering Client Computers
	---------------------------
	
	To clean up any remaining drive letters on clients, it is necessary to delete the
	drive letters that are defined in the client's registry at the following
	registry key:
	
	  HKEY_USERS\.Default\Network
	
	One possible method for automating this operation is to use the Reg.exe utility
	that is included with the Windows 2000 Support Tools. You can run the "REG
	DELETE HKEY_USERS\.DEFAULT\Network /F" (without the quotation marks) command on
	the client to remove all of the drive mappings that were created by the SMS
	client by deleting the Network registry value.
	
	NOTE: By default, this registry key does not exist, and user's persistent drive
	mappings are stored under their own profile under HKEY_USERS or
	HKEY_CURRENT_USER. Because of this, a user's personal settings are not
	affected.
	
	
	Additional query words: prodsms
	
	======================================================================
	Keywords          : kbenv kberrmsg kbtool kbsms200 kbsms200bug kbsms200fix kbAdvertisement kbPackage kbSoftwareDist kbsms200preSP4fix 
	Technology        : kbSMSSearch kbSMS200SP2 kbSMS200SP3
	Version           : :2.0 SP2,2.0 SP3
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
