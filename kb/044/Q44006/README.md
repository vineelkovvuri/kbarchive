---
layout: page
title: "Q44006: CodeView Requires PUBLIC to Trace MASM Program in Source Mode"
permalink: /kb/044/Q44006/
---

## Q44006: CodeView Requires PUBLIC to Trace MASM Program in Source Mode

{% raw %}

	Article: Q44006
	Product(s): See article
	Version(s): 2.20
	Operating System(s): MS-DOS
	Keyword(s): ENDUSER | H_MASM | mspl13_basic
	Last Modified: 3-MAY-1989
	
	A MASM program that runs perfectly from a DOS prompt refuses to trace
	in source mode inside of CodeView. The program single-steps in
	assembly mode, but an attempt to trace into the code in source mode
	results in the program terminating upon reaching the first data
	declaration.
	
	In addition, the program does not come up in source mode when CodeView
	is started, but can be changed into source mode with "View" "Source".
	
	This problem happens when the code and data segments are not declared
	as "PUBLIC". The code is valid and executes perfectly inside of
	CodeView or from a DOS prompt. However, CodeView cannot follow the
	logic at a source level.
	
	A program constructed in the following manner exhibits the symptoms
	described above:
	
	TITLE    myprog
	
	StackSeg Segment STACK
	.
	.
	.
	DataSeg  Segment DATA
	.
	.
	.
	CodeSeg  Segment CODE
	.
	.
	.
	END      myprog
	
	However, if the following minor changes are made to the program, and
	the segments are declared as "PUBLIC", CodeView can trace through the
	program in source mode:
	
	TITLE    myprog
	
	StackSeg Segment STACK
	.
	.
	.
	DataSeg  Segment WORD PUBLIC 'DATA'
	.
	.
	.
	CodeSeg  Segment WORD PUBLIC 'CODE'
	.
	.
	.
	END      myprog

{% endraw %}
