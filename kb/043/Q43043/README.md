---
layout: page
title: "Q43043: CodeView Protect: /43 Switch Doesn't Work on VGA Adapters"
permalink: /kb/043/Q43043/
---

## Q43043: CodeView Protect: /43 Switch Doesn't Work on VGA Adapters

{% raw %}

	Article: Q43043
	Product(s): See article
	Version(s): 2.20
	Operating System(s): OS/2
	Keyword(s): ENDUSER | buglist2.20 | mspl13_basic
	Last Modified: 18-APR-1989
	
	The /43 switch for CodeView, used to debug in 43 line mode, is ignored
	when a VGA video adapter is being used under OS/2. This switch works
	properly as documented in DOS, or when an EGA adapter is being used.
	The /50 switch, used to debug in 50 line mode, also works properly as
	documented.
	
	If you wish to use CodeView Version 2.20 in 43 line mode under OS/2,
	the MODE command can be used first to set the entire screen group into
	43 line mode. Using MODE 80,43 at the OS/2 prompt will accomplish this
	result. Starting CodeView without any switches will then cause it to
	use the current video mode.
	
	Microsoft has confirmed this to be a problem in CodeView Protect
	Version 2.20. This feature is under review and will be considered for
	inclusion in a future release.

{% endraw %}
