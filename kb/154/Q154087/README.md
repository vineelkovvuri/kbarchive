---
layout: page
title: "Q154087: Access Violation in Lsass.exe Due to Incorrect Buffer Size"
permalink: /kb/154/Q154087/
---

## Q154087: Access Violation in Lsass.exe Due to Incorrect Buffer Size

{% raw %}

	Article: Q154087
	Product(s): Microsoft Windows NT
	Version(s): winnt:4.0,4.0 SP3
	Operating System(s): 
	Keyword(s): kberrmsg kbfile kbWinNT400sp4fix
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Workstation version 4.0 SP3 
	- Microsoft Windows NT Server version 4.0 SP3 
	- Microsoft Windows NT Server version 4.0, Terminal Server Edition 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	While running Windows NT, you may receive an Access Violation error message in
	Lsass.exe. After this error occurs, you cannot logon locally and the
	administrative tools that rely on LSA/LSARPC (such as Event Viewer and Server
	Manager) do not function.
	
	CAUSE
	=====
	
	The failure occurs when a remote client connects to the Local Security Authority
	over a named pipe and passes an incorrect buffer size (fragment length).
	
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for Windows NT 4.0 or
	Windows NT Server 4.0, Terminal Server Edition. For additional information,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q152734 How to Obtain the Latest Windows NT 4.0 Service Pack
	
	
	Microsoft has updated Lsasrv.dll to correct this problem and posted the updated
	version to the following Internet location.
	
	NOTE: Lsa-fix has been superseded by Lsa2-fix.
	
	For your convenience, the English version of this post-SP3 hotfix has been posted
	to the following Internet location. However, Microsoft recommends that you
	install Windows NT 4.0 Service Pack 4 to correct this problem.
	
	ftp://ftp.microsoft.com/bussys/winnt/winnt-public/fixes/usa/NT40/
	hotfixes-postSP3/lsa2-fix/
	
	You can find the (http://support.microsoft.com/download/support/mslfiles/the)
	original hotfix at the following Microsoft ftp site:
	
	ftp://ftp.microsoft.com/bussys/winnt/winnt-public/fixes/usa/NT40/
	hotfixes-postSP3/archive/lsa-fix/
	
	WARNING: If you install the original (archived) version of this hotfix AFTER you
	apply the later version, your system may become unusable. Microsoft does not
	recommend you install the original hotfix after applying the later version.
	
	STATUS
	======
	
	Microsoft has confirmed this problem could result in some degree of security
	vulnerability in Windows NT version 4.0. This problem was first corrected in
	Windows NT 4.0 Service Pack 4.0 and Windows NT Server 4.0, Terminal Server
	Edition Service Pack 4.
	
	
	
	Additional query words: 4.00
	
	======================================================================
	Keywords          : kberrmsg kbfile kbWinNT400sp4fix 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400search kbWinNT400search kbWinNTW400sp3 kbWinNTSsearch kbWinNTS400sp3 kbWinNTS400search kbNTTermServ400 kbNTTermServSearch
	Version           : winnt:4.0,4.0 SP3
	Hardware          : ALPHA x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
