---
layout: page
title: "Q258614: HTML Filter Emits DocAuthor Property Instead of the Title"
permalink: /kb/258/Q258614/
---

## Q258614: HTML Filter Emits DocAuthor Property Instead of the Title

{% raw %}

	Article: Q258614
	Product(s): Internet Information Server
	Version(s): 2.0,3.0,4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Site Server version 3.0 
	- Microsoft Index Server version 2.0 
	- Indexing Service, on platform(s):
	   - the operating system: Microsoft Windows 2000 
	   - the operating system: Microsoft Windows NT 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you search for HTML-converted Microsoft Word documents, the summary shows
	the XML document properties.
	
	CAUSE
	=====
	
	The Microsoft Office properties (located in the XML island) in a Microsoft
	Office document that is saved as an HTML file are emitted as text content.
	
	WORKAROUND
	==========
	
	Put a description meta tag in the generated HTML document to override the
	abstract properties.
	
	RESOLUTION
	==========
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem that is described in this article. Apply it only to
	computers that are experiencing this specific problem. This fix may receive
	additional testing. Therefore, if you are not severely affected by this problem,
	Microsoft recommends that you wait for the next Windows NT, Windows 2000 or Site
	Server service pack that contains this fix.
	
	To resolve this problem immediately, contact Microsoft Product Support Services
	to obtain the fix. For a complete list of Microsoft Product Support Services
	phone numbers and information about support costs, visit the following Microsoft
	Web site:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	NOTE: In special cases, charges that are ordinarily incurred for support calls
	may be canceled if a Microsoft Support Professional determines that a specific
	update will resolve your problem. The typical support costs will apply to
	additional support questions and issues that do not qualify for the specific
	update in question.
	
	The English version of this fix should have the following file attributes or
	later:
	
	  Date       Time    Version      Size    File name     Platform
	  -------------------------------------------------------------
	  07/13/2000 02:36   7.0.1313.0   101.872 Nlhtml.dll    x86
	  07/13/2000 18:54   7.0.1313.0   190,224 Nlhtml.dll    alpha
	
	
	
	STATUS
	======
	
	Microsoft has confirmed that this is a problem in the Microsoft products that
	are listed at the beginning of this article.
	
	MORE INFORMATION
	================
	
	The fix for Q258614 also resolves further issues with script code appearing in
	the abstracts returned in a query result.
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbSiteServSearch kbIdxServSearch kbAudDeveloper kbIdxServ100
	Version           : :2.0,3.0,4.0
	Hardware          : ALPHA x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
