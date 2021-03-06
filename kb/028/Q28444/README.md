---
layout: page
title: "Q28444: Example of Calling OS/2 DosGetVersion and DosGetMachineMode"
permalink: /kb/028/Q28444/
---

## Q28444: Example of Calling OS/2 DosGetVersion and DosGetMachineMode

{% raw %}

	Article: Q28444
	Product(s): See article
	Version(s): 6.00 6.00b 7.00 | 6.00 6.00b 7.00
	Operating System(s): MS-DOS | OS/2
	Keyword(s): ENDUSER | | mspl13_basic
	Last Modified: 2-FEB-1990
	
	Below is a sample program that makes calls to the OS/2 functions
	DosGetVersion and DosGetMachineMode.
	
	' The function declarations are found in BSEDOSPC.BI
	
	DECLARE FUNCTION DosGetVersion%(_
	        SEG P1 AS INTEGER)
	
	DECLARE FUNCTION DosGetMachineMode(_
	        BYVAL P1s AS INTEGER,_
	        BYVAL P1o AS INTEGER)
	
	DEFINT A-Z
	CLS
	DIM mode AS STRING*1
	
	x=DosGetMachineMode%(varseg(mode),varptr(mode))
	IF (x) THEN
	   Print "An error occurred. The number is : ";x
	ELSE
	   IF mode=chr$(0) THEN
	      print "Real Mode"
	   ELSE
	      print "Protect Mode"
	   END if
	END IF
	
	x=DosGetVersion(version)
	IF (x) THEN
	   Print "An error occurred. The number is : ";x
	ELSE
	   Print "The version number is : ";
	   Print  peek(varptr(version)+1);".";peek(varptr(version))
	END IF

{% endraw %}
