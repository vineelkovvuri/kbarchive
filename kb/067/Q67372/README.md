---
layout: page
title: "Q67372: Recursive CALL in 7.0 .EXE Forgets Parent's Passed Near String"
permalink: /kb/067/Q67372/
---

## Q67372: Recursive CALL in 7.0 .EXE Forgets Parent's Passed Near String

{% raw %}

	Article: Q67372
	Product(s): See article
	Version(s): 7.00   | 7.00
	Operating System(s): MS-DOS | OS/2
	Keyword(s): ENDUSER | SR# S901116-127 buglist7.00 fixlist7.10 | mspl13_basic
	Last Modified: 5-DEC-1990
	
	When the first layer (first call) of a recursive procedure passes a
	near string to the next layer of recursion, the value of the initial
	string passed by the parent recursive layer is forgotten within the
	parent SUB after returning from subsequent recursive layers of the
	routine. This problem does not occur if you compile with far strings
	(BC /Fs).
	
	This problem applies to Microsoft BASIC Professional Development
	System (PDS) version 7.00 for MS-DOS and MS OS/2. This problem has
	been corrected in BASIC PDS version 7.10.
	
	The code below demonstrates the problem when passing a near string in
	a recursive subprogram CALL. You can work around the problem by
	compiling with far strings.
	
	CLS
	CALL RecCall("A")
	END
	
	SUB RecCall (Text AS STRING)
	   PRINT Text; "<"
	   IF Text <> "B" THEN
	      CALL RecCall (CHR$(ASC(Text) + 1))
	      'Could use CALL ReCall("B") with same problem
	   END IF
	   PRINT Text; "<"
	END SUB
	
	   Compiled with   Interpreted in QBX.EXE
	   Near String     or Compiled with Far
	   (Problem)       String Option (No Problem)
	   -------------   --------------------------
	      >A               >A
	      >B               >B
	      >B               >B
	      >                >A

{% endraw %}
