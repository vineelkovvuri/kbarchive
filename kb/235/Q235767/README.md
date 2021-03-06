---
layout: page
title: "Q235767: SMS: Programs Fail to Run From a Package Subdirectory"
permalink: /kb/235/Q235767/
---

## Q235767: SMS: Programs Fail to Run From a Package Subdirectory

{% raw %}

	Article: Q235767
	Product(s): Microsoft Systems Management Server
	Version(s): winnt:2.0
	Operating System(s): 
	Keyword(s): kbsms200 kbsms200bug
	Last Modified: 11-JUL-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server version 2.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Microsoft's Systems Management Server version 2.0 offers an administrator the
	option of browsing to the location where the source files are when creating
	packages.
	
	When an administrator uses the browse button and traverses the directory
	structure to the source file, a bad source path will be created if any of the
	directory names contain at least two words with a space between them. Normally,
	an administrator would surround the directory name with double quotes in order
	to let the Operating System know that this is the name of a single directory.
	
	An example of this might be:
	
	x:\WINNT\Software\Source Files
	
	The directory SOURCE FILES would cause a problem if the Administrator did not
	catch this and add double quotes around the directory name. Once the
	Administrator caught the omission, the path would appear like the following:
	
	x:\WINNT\Software\"Source Files"
	
	When the Administrator confirms the source path in the Admin Console, it would be
	correct on appearance based on what the Windows Explorer might display. The
	system would not automatically surround the directory name with double quotes.
	When the instruction file is called to execute the package an Advertisement and
	the source path run, this would generate a failure since the path in the
	Instruction file would be incorrect.
	
	This issue is more likely to arise in an environment running Windows 2000 since
	the number of paths with spaces is dramatically increased from that of Windows
	NT Server 4.0.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Systems Management Server
	version 2.0. This problem has been corrected in the latest U.S. service pack for
	Systems Management Server version 2.0. For information on obtaining the service
	pack, query on the following word in the Microsoft Knowledge Base (without the
	spaces):
	
	  S E R V P A C K
	
	MORE INFORMATION
	================
	
	Errors for this type of problem would normally appear within the Smsapm32.log
	file on the client computer.
	
	Additional query words: prodsms
	
	======================================================================
	Keywords          : kbsms200 kbsms200bug 
	Technology        : kbSMSSearch kbSMS200
	Version           : winnt:2.0
	Issue type        : kbbug
	
	=============================================================================
	

{% endraw %}
