---
layout: page
title: "Q43001: Fopen() Description Is Incomplete in On-Line Help of QC 2.00"
permalink: /kb/043/Q43001/
---

## Q43001: Fopen() Description Is Incomplete in On-Line Help of QC 2.00

{% raw %}

	Article: Q43001
	Product(s): See article
	Version(s): 2.00
	Operating System(s): MS-DOS
	Keyword(s): ENDUSER | docerr | mspl13_c
	Last Modified: 2-MAY-1989
	
	The information given in the Microsoft QuickC Compiler Version 2.00
	on-line help for the fopen() function is incomplete. The following is
	a more complete description of the "type" parameter, taken from Page
	274 of the "Microsoft QuickC Version 2.00 Run-Time Library Reference"
	manual.
	
	The character string "type" specifies the type of access requested for
	the file, as follows:
	
	Type     Description
	
	"r"      Opens for reading. If "r" is the first character in type, and
	         the file does not exist or cannot be found, the fopen call
	         will fail.
	
	"w"      Opens an empty file for writing. If the given file exists,
	         its contents are destroyed.
	
	"a"      Opens for writing at the end of the file (appending); creates
	         the file first if it doesn't exist.
	
	"r+"     Opens for both reading and writing. (The file must exist.)
	
	"w+"     Opens an empty file for both reading and writing. If the
	         given file exists, its contents are destroyed.
	
	"a+"     Opens for reading and appending; creates the file first if it
	         doesn't exist.
	
	Please note: Use the "w" and "w+" types with care, as they can destroy
	existing files.

{% endraw %}
