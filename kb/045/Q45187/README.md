---
layout: page
title: "Q45187: Documented Search Order for Include Files"
permalink: /kb/045/Q45187/
---

## Q45187: Documented Search Order for Include Files

{% raw %}

	Article: Q45187
	Product(s): See article
	Version(s): 5.00 5.10 | 5.10
	Operating System(s): MS-DOS | OS/2
	Keyword(s): ENDUSER | docerr | mspl13_c
	Last Modified: 18-SEP-1989
	
	I am having trouble determining the precise search order for include
	files. The Version 5.10 "Microsoft C for the MS-DOS Operating System:
	User's Guide" states the following on Page 34:
	
	   The compiler always searches the current working directory first
	   before searching the locations given in the environment variable.
	
	(Except when using < >).
	
	The Version 5.10 "Microsoft C for the MS-DOS Operating System:
	Language Reference" on Page 203 discusses searching in terms of the
	"parent" file's directory, then also mentions the current working
	directory in a subsequent paragraph.
	
	From my experimenting, it seems that all references to the current
	working directory are incorrect. The compiler actually searches based
	on the parent's directory. The MS-DOS current directory is never
	searched unless it is included on the command line or in the INCLUDE
	variable.
	
	The above assumptions are correct. All references to the "current
	working directory" should be referring to the "parent" directory. This
	is a documentation error. If include files are nested, then this error
	becomes important. With nested include files, the current working
	directory can be very different from the parent directory. The parent
	directory is always the one that is searched.

{% endraw %}
