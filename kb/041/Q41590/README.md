---
layout: page
title: "Q41590: QuickC 2.00 README.DOC: Example Program GRAPHIC.C"
permalink: /kb/041/Q41590/
---

## Q41590: QuickC 2.00 README.DOC: Example Program GRAPHIC.C

{% raw %}

	Article: Q41590
	Product(s): See article
	Version(s): 2.00
	Operating System(s): MS-DOS
	Keyword(s): ENDUSER | | mspl13_c
	Last Modified: 28-FEB-1989
	
	The following information is taken from the QuickC Version 2.00
	README.DOC file, part 2 "Notes on "'C for Yourself.'" The following
	notes refer to specific pages in "C for Yourself."
	
	Page 209   Example Program GRAPHIC.C
	
	The declaration at the beginning of GRAPHIC.C should be
	
	   struct videoconfig screen;
	
	Also, change the seventh constant in the array 'modes' to _ERESNOCOLOR
	and remove the semicolon at the end of line that begins the "while"
	loop.
	
	The GRAPHIC.C program in on-line help already contains these
	corrections, but you may want to correct the printed listing, too.

{% endraw %}
