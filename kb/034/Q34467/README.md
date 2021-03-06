---
layout: page
title: "Q34467: MASM 5.10 MACRO.DOC: DOS Macro Syntax and Description"
permalink: /kb/034/Q34467/
---

## Q34467: MASM 5.10 MACRO.DOC: DOS Macro Syntax and Description

{% raw %}

	Article: Q34467
	Product(s): See article
	Version(s): 5.10   | 5.10
	Operating System(s): MS-DOS | OS/2
	Keyword(s): ENDUSER | | mspl13_masm
	Last Modified: 12-JAN-1989
	
	The following information was taken from the MASM 5.10 MACRO.DOC file.
	
	DOS Macro Syntax and Description
	
	KEYBOARD INPUT
	
	@GetKey (01h, 07h, 08h, 0Ch)
	
	Gets a keystroke from the keyboard
	
	Syntax:         @GetKey [#echo] [,[#break] [,#clearbuf]]
	
	Arguments:      echo        = nonzero to echo keystroke -
	                              default yes
	                break       = nonzero to accept Control-C - default
	                              yes
	                clearbuf    = nonzero to clear keyboard buffer -
	                              default no
	                (Arguments may be omitted to get defaults)
	Return:         ASCII code of key in AL
	Registers used: AX used for all, DL used if echo on and ctrl
	-c off
	
	@GetStr (0Ah)
	
	Gets a string from the keyboard
	
	Syntax:         @GetStr &buffer [,[$terminator] [,[#limit]
	[,segment]]]
	
	Arguments:      buffer      = Offset of buffer where string will
	                              be stored
	                    Byte 1  = Maximum length of string (before call)
	                    Byte 2  = Actual length of string (after call)
	                    Byte 3+ = Bytes of string
	                terminator  = Terminating byte - usually null (0) or
	$ (24h)
	                limit       = Maximum length of string (if not given
	                              as argument, must be in buffer before
	                              macro call)
	                segment     = Segment of buffer (DS if not given)
	Return:         Pointer to string in SI, length of string in BX
	Registers used: AX, DX, BX, SI

{% endraw %}
