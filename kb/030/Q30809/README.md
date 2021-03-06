---
layout: page
title: "Q30809: MASM 5.10 OS2.DOC: OS/2 Call Summary - Module Management"
permalink: /kb/030/Q30809/
---

## Q30809: MASM 5.10 OS2.DOC: OS/2 Call Summary - Module Management

{% raw %}

	Article: Q30809
	Product(s): See article
	Version(s): 5.10   | 5.10
	Operating System(s): MS-DOS | OS/2
	Keyword(s): ENDUSER | | mspl13_masm
	Last Modified: 27-MAY-1988
	
	The following information is from the Microsoft Macro Assembler
	Version 5.10 OS2.DOC file.
	
	OS/2 Call Summary
	Module management constant - INCL_DOSMODULEMGR
	
	   @DosLoadModule - Loads a dynamic-link module and assigns it a handle
	   Parameters - ObjNameBufAdd:PD, ObjNameBufL:W, ModuleName:PZ,
	                ModuleHandle:PW
	
	   @DosFreeModule - Frees a reference to a dynamic-link module
	   Parameters - ModuleHandle:W
	
	   @DosGetProcAddr - Returns the far address of a procedure within a
	                     dynamic-link module
	   Parameters - ModuleHandle:W, ProcName:PZ, ProcAddress:PD
	
	   @DosGetModHandle - Tests whether a specified dynamic-link module is loaded
	   Parameters - ModuleName:PZ, ModuleHandle:PW
	
	   @DosGetModName - Returns the complete pathname of a specified module
	   Parameters - ModuleHandle:W, BufferLength:W, Buffer:PB

{% endraw %}
