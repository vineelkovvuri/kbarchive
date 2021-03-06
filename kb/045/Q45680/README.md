---
layout: page
title: "Q45680: Error C4096: &quot;Unkown Warning&quot; May Be Caused by C1.ERR Omission"
permalink: /kb/045/Q45680/
---

## Q45680: Error C4096: &quot;Unkown Warning&quot; May Be Caused by C1.ERR Omission

{% raw %}

	Article: Q45680
	Product(s): See article
	Version(s): 2.01
	Operating System(s): MS-DOS
	Keyword(s): ENDUSER | docerr | mspl13_masm
	Last Modified: 28-JUN-1989
	
	An error was made in the file C1.ERR, which is included in the
	Microsoft QuickAssembler package, where one error listing was omitted.
	
	This omission produces the following warning whenever you compile a C
	program and have the "Generate Com file" option chosen in the menu
	Options.Make.Linker Flags:
	
	   C4096: UNKNOWN WARNING
	          Contact Microsoft Technical Support
	
	This warning is not "unknown"; rather, it is just omitted. Actually, C4096
	means the following:
	
	   C4096    "-AT treated as -AS"
	
	To correct this problem, you need only insert the following line in
	the file C1.ERR:
	
	   C4096    "-AT treated as -AS"
	
	You should insert this line into the file so that it is correctly
	ordered (i.e., C4096 should follow C4095...).
	
	This ommission will be corrected in subsequent releases of the
	QuickAssembler package.

{% endraw %}
