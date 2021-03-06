---
layout: page
title: "Q51323: Using CodeView to Create Disassembled Program Listings"
permalink: /kb/051/Q51323/
---

## Q51323: Using CodeView to Create Disassembled Program Listings

{% raw %}

	Article: Q51323
	Product(s): See article
	Version(s): 2.20 2.30 | 2.20 2.30
	Operating System(s): MS-DOS | OS/2
	Keyword(s): ENDUSER | | mspl13_basic
	Last Modified: 12-APR-1990
	
	The following steps can be used to create an assembly listing of a
	program with CodeView:
	
	1. Begin CodeView in sequential mode by using the /T command-line
	   switch.
	
	2. Specify a listing file to redirect CodeView output to by typing the
	   redirection operator ">" followed by a filename at the dialog
	   prompt. You may redirect the output directly to a printer by
	   specifying the printer after the ">" (e.g., >PRN).
	
	   (Note: From this point on, commands will not be viewable.)
	
	3. Use the Unassemble command "U" to disassemble the code and send a
	   listing of the program to the output file. If you do not specify
	   the starting address and the range to unassemble, CodeView will
	   unassemble the next eight lines of code. See the CodeView
	   documentation for more information on the Unassemble command.
	
	You can use this method on any files, whether or not they contain
	CodeView information. In this regard, you can create assembly listings
	of programs that were not created with a Microsoft compiler. Please
	also note that you cannot create assembly listings of instructions
	other than 8086 instructions.

{% endraw %}
