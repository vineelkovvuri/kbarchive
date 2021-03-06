---
layout: page
title: "Q31658: CVP Prompts &quot;SYS0197 OS/2 Not Configured...&quot; Error Message"
permalink: /kb/031/Q31658/
---

## Q31658: CVP Prompts &quot;SYS0197 OS/2 Not Configured...&quot; Error Message

{% raw %}

	Article: Q31658
	Product(s): See article
	Version(s): 2.20
	Operating System(s): OS/2
	Keyword(s): ENDUSER | | mspl13_basic
	Last Modified: 9-NOV-1988
	
	When loading CodeView protected mode (CVP), the "SYS0197 OS/2 not
	configured to run this application" error message may appear. A
	request for help on 0197 prompts the "requires input/output privilege"
	message. You need to set IOPL=YES in CONFIG.SYS to run CVP.
	
	   The following information is from the section titled "Microsoft(R)
	CodeView(R) Debugger" of the Microsoft C Version 5.10 UTILITY.DOC
	file, the FORTRAN Version 4.10 CVREADME.DOC file, and the Microsoft
	Macro Assembler Version 5.10 README.DOC file.
	
	CONFIG.SYS Setting for CVP
	   To run the protected-mode CodeView debugger (CVP.EXE), you must
	have the following line in your CONFIG.SYS file:
	
	   IOPL=YES

{% endraw %}
