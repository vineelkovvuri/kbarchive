---
layout: page
title: "Q314342: SMS: Advertisements May Not Run If the Screen Saver Runs"
permalink: /kb/314/Q314342/
---

## Q314342: SMS: Advertisements May Not Run If the Screen Saver Runs

{% raw %}

	Article: Q314342
	Product(s): Microsoft Systems Management Server
	Version(s): 2.0
	Operating System(s): 
	Keyword(s): kberrmsg kbtool kbsms200preSP4fix
	Last Modified: 06-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server version 2.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If you specify that an advertisement for a program should run only when a user
	is not logged on, the advertisement may not run if a screen saver runs.
	
	In the <Path>\Ms\Sms\Logs\Smsapm32.log (where <Path> is the path to
	the Ms folder) file, the following information may be logged when a user is not
	logged on to the computer and the screen saver is running:
	
	  SCHEDULER : This job needs to be run when there is no user logged on.
	  SCHEDULER : Checking if a user is actually logged off.
	  SCHEDULER : The user is not logged off the system.
	  SCHEDULER : This job requires the user to be logged off the system.
	  SCHEDULER : Attempting to schedule this job at some time in the future when
	  the logoff process has completed.
	
	CAUSE
	=====
	
	The Advertised Programs Manager Systems Management Server (SMS) component
	verifies that there is a default interactive desktop on a client computer to
	determine whether the user is logged off. The default desktop is not available
	after a user is logged off, however, a new interactive desktop is created if a
	screen saver runs. When this interactive desktop is created, Advertised Program
	Manager does not correctly differentiate between the interactive desktop and the
	default desktop that is used by the user who is logged on. When this problem
	occurs, Advertised Programs Manager incorrectly determines that the default
	interactive desktop is present and that the user is logged on.
	
	RESOLUTION
	==========
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem that is described in this article. Only apply it to systems
	that are experiencing this specific problem. This fix may receive additional
	testing. Therefore, if you are not severely affected by this problem, Microsoft
	recommends that you wait for the next Systems Management Server service pack
	that contains this fix.
	
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
	
	  Date         Version         Size       File name            Platform
	  ---------------------------------------------------------------------
	  01-MAR-2001                    654,488  Apasetup.exe         Alpha  
	  01-MAR-2001  2.00.1493.3216    293,648  Ccim32.dll           Alpha
	  01-MAR-2001                  1,925,224  Ccmcore.exe          Alpha
	  01-MAR-2001  2.00.1493.3214  1,938,192  Clibase.dll          Alpha
	  01-MAR-2001                  4,441,916  Clicore.exe          Alpha
	  01-MAR-2001  2.00.1493.3216    125,712  Clisvcl.exe          Alpha
	  01-MAR-2001  2.00.1493.3216     13,584  Cliver.exe           Alpha
	  01-MAR-2001                         67  Compverbase.ini      Alpha
	  01-MAR-2001                         67  Compversmsapm32.ini  Alpha
	  01-MAR-2001                         67  Compverswdist.ini    Alpha
	  01-MAR-2001  2.00.1493.3216     66,832  Cqmgr32.dll          Alpha
	  01-MAR-2001  2.00.1493.3215    578,832  Mslmclin.dll         Alpha
	  01-MAR-2001  2.00.1493.3216     73,488  ODPSYS32.exe         Alpha
	  01-MAR-2001  2.00.1493.3216     82,192  Odpusr32.exe         Alpha
	  01-MAR-2001  2.00.1493.3218    382,224  Smsapm32.exe         Alpha
	  01-MAR-2001                    691,596  Swdist32.exe         Alpha
	
	  01-MAR-2001                    394,061  Apasetup.exe         Intel
	  01-MAR-2001  2.00.1493.3125    259,936  Bindclin.dll         Intel
	  01-MAR-2001  2.00.1493.3216    181,584  Ccim32.dll           Intel
	  01-MAR-2001                  1,324,069  Ccmcore.exe          Intel
	  01-MAR-2001  2.00.1493.3214  1,222,560  Clibase.dll          Intel
	  01-MAR-2001                  3,401,546  Clicore.exe          Intel
	  01-MAR-2001  2.00.1493.3216     88,432  Clisvcl.exe          Intel
	  01-MAR-2001  2.00.1493.3216      8,512  Cliver.exe           Intel
	  01-MAR-2001                         67  Compverbase.ini      Intel
	  01-MAR-2001                         67  Compversmsapm32.ini  Intel
	  01-MAR-2001                         67  Compverswdist.ini    Intel
	  01-MAR-2001  2.00.1493.3216     39,264  Cqmgr32.dll          Intel
	  01-MAR-2001  2.00.1493.3125    338,272  Mslmclin.dll         Intel
	  01-MAR-2001  2.00.1493.3125    269,664  Ndsclin.dll          Intel
	  01-MAR-2001  2.00.1493.3216     53,104  Odpsys32.exe         Intel
	  01-MAR-2001  2.00.1493.3216     59,248  Odpusr32.exe         Intel
	  01-MAR-2001  2.00.1493.3218    287,088  Smsapm32.exe         Intel
	  01-MAR-2001                    637,723  Swdist32.exe         Intel
	
	NOTE: Due to file dependencies, the most recent hotfix or feature that contains
	the above files may also contain additional files.
	
	
	
	STATUS
	======
	
	Microsoft has confirmed that this is a problem in the Microsoft products that
	are listed at the beginning of this article. This problem was first corrected in
	the Systems Management Server 2.0 Service Pack 4 Hotfix Rollup Package (HRP).
	
	For additional information about the SMS 2.0 SP4 HRP, click the article number
	below to view the article in the Microsoft Knowledge Base:
	
	  Q323206 SMS: List of Bugs Fixed in the Systems Management Server 2.0 SP4 HRP
	
	MORE INFORMATION
	================
	
	After you install the hotfix that is described in this article, the Advertised
	Programs Manager SMS component determines the type of desktop that is returned
	and differentiates between the screen saver and the default variations of the
	interactive desktop.
	
	
	Additional query words: advert apm
	
	======================================================================
	Keywords          : kberrmsg kbtool kbsms200preSP4fix 
	Technology        : kbSMSSearch kbSMS200
	Version           : :2.0
	Hardware          : x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
