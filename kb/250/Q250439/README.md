---
layout: page
title: "Q250439: STOP 0x0000000A While Printing in Windows NT 4.0"
permalink: /kb/250/Q250439/
---

## Q250439: STOP 0x0000000A While Printing in Windows NT 4.0

{% raw %}

	Article: Q250439
	Product(s): Microsoft Windows NT
	Version(s): winnt:4.0
	Operating System(s): 
	Keyword(s): kberrmsg kbprint
	Last Modified: 08-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 4.0, Terminal Server Edition 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you try to print from a computer running Windows NT 4.0 or Windows NT 4.0,
	Terminal Server Edition, you may receive the following blue screen error
	message:
	
	  STOP 0x0000000A (0x00000000, 0x00000002, 0x00000000, 0x80109727)
	
	NOTE: The fourth parameter varies depending on the version of Windows NT you are
	using, but always reports the Ntoskrnl.exe file.
	
	CAUSE
	=====
	
	This issue can occur if the printer .dll files are started twice.
	
	RESOLUTION
	==========
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem described in this article and should be applied only to
	systems experiencing this specific problem. This fix may receive additional
	testing at a later time, to further ensure product quality. Therefore, if you
	are not severely affected by this problem, Microsoft recommends that you wait
	for the next Windows NT 4.0 service pack that contains this fix.
	
	To resolve this problem immediately, contact Microsoft Product Support Services
	to obtain the fix. For a complete list of Microsoft Product Support Services
	phone numbers and information about support costs, please go to the following
	address on the World Wide Web:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	NOTE: In special cases, charges that are normally incurred for support calls may
	be canceled, if a Microsoft Support Professional determines that a specific
	update will resolve your problem. Normal support costs will apply to additional
	support questions and issues that do not qualify for the specific update in
	question.
	
	The English-language version of this fix should have the following file
	attributes or later:
	
	  Date      Time     Size       File name    Platform
	  ---------------------------------------------------
	  12/23/99   3:24p    170,256   gdi32.dll    Intel
	  12/20/99   1:04p    331,436   user32.dll   Intel
	  1/18/00    8:41p  1,274,768   win32k.sys   Intel
	  1/20/99    1:08p    195,856   winsrv.dll   Intel 
	
	
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT 4.0.
	
	Additional query words:
	
	======================================================================
	Keywords          : kberrmsg kbprint 
	Technology        : kbWinNTsearch kbWinNT400search kbWinNTSsearch kbWinNTS400search kbNTTermServ400 kbNTTermServSearch
	Version           : winnt:4.0
	Hardware          : ALPHA x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
