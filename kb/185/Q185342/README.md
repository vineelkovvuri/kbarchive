---
layout: page
title: "Q185342: SMS: How to Install, Share, and Inventory Software"
permalink: /kb/185/Q185342/
---

## Q185342: SMS: How to Install, Share, and Inventory Software

{% raw %}

	Article: Q185342
	Product(s): Microsoft Systems Management Server
	Version(s): winnt:1.1
	Operating System(s): 
	Keyword(s): kbfaq
	Last Modified: 02-SEP-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server version 1.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	You can use Systems Management Server to do the following tasks:
	
	- Package Command Manager (PCM) Install software on selected workstations
	  throughout your enterprise.
	
	- Program Group Control (PGC) Install software on distribution servers, where
	  it can be shared by specified workstations .
	
	- Inventory Perform an inventory or audit of the software installed on
	  networked computers.
	
	MORE INFORMATION
	================
	
	To complete the tasks described above, complete following steps:
	
	1. Create a source directory, share the directory, and copy the installation
	  files to it. (Note that this is not applicable for software inventory.)
	
	2. In the Systems Management Server Administrator program, create a package that
	  uses the source directory specified in step 1 and contains instructions for
	  executing the package on the target clients and support operating systems.
	
	3. In the Systems Management Server Administrator program, create a job
	  explaining where to send the package. Note that this step is not necessary
	  for inventory packages.
	
	Systems Management Server compresses a package before sending it to the target
	site, thus reducing the amount of traffic on the network as the package is
	passed through the site hierarchy.
	
	When the target site server receives the package, it places the package on one or
	more distribution servers, and places the installation, sharing, or inventory
	instructions for the target computers on the appropriate logon servers.
	
	The three steps above are common for all types of packages. However, depending on
	the defined package properties, Systems Management Server handles each package
	differently. Systems Management Server uses the following properties to define
	packages:
	
	- Workstation properties are used to install a package on the clients (Run
	  Command On Workstation jobs).
	
	- Sharing properties are used to install a package on each of the servers and
	  then share it from those servers (Share Package On Server jobs).
	
	- Inventory properties are used to maintain inventory on a package.
	
	You can define any (or all) of these properties for any package. You can also add
	or modify properties after the package has been created.
	
	Systems Management Server includes package definition files (PDFs) and
	configuration scripts for many popular Microsoft applications and operating
	systems. If you are creating a package to distribute a Microsoft application,
	you can use a PDF to define many package properties for you.
	
	Additional query words: prodsms
	
	======================================================================
	Keywords          :  kbfaq
	Technology        : kbSMSSearch kbSMS110
	Version           : winnt:1.1
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
