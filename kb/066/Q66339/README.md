---
layout: page
title: "Q66339: MASM Build Switches for PWB 1.10"
permalink: /kb/066/Q66339/
---

## Q66339: MASM Build Switches for PWB 1.10

{% raw %}

	Article: Q66339
	Product(s): Microsoft Programming Utilities
	Version(s): MS-DOS:1.1; OS/2:1.1
	Operating System(s): 
	Keyword(s): kb16bitonly
	Last Modified: 31-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Programmer's Workbench for MS-DOS, version 1.1 
	- Microsoft Programmer's Workbench for OS/2, version 1.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	When setting a program list containing .ASM files in Programmer's WorkBench
	(PWB) version 1.10, the following error message occurs:
	
	  Program List: file 'filename' will be ignored
	  File type unused by current build options
	
	The .ASM files are not recognized because PWB 1.1 does not contain build switches
	specific to any language. Build switches are now loaded from language extension
	files (.MXT for DOS and .PXT for OS/2). If you have an assembly language
	extension file, you will not see this error message. Language extensions are not
	necessary and are only a convenience for controlling the build process; only the
	build switches are really needed.
	
	The sample build switches below can be added to a tagged section in your
	TOOLS.INI file. To use these build options, initialize the tagged section by
	typing {arg} tag_name {reinitialize}, which is equivalent to the following
	keystrokes for the sample build switches below:
	
	  ALT+A asm_rules SHIFT+F8
	
	Note that if you are doing mixed-language programming, you should first set your
	main language and initial build options from the Build Options dialog box under
	the Options menu and then initialize the tagged section.
	
	The MASM build switches can also be added to a custom set of build options saved
	by Save Current Build Options. They may then be initialized by choosing Build
	Options from the Options menu, and then selecting Set Initial Build Options to
	choose the new custom language options.
	
	MORE INFORMATION
	================
	
	Sample Build Switches
	---------------------
	
	  [pwb-asm_rules]
	  ;
	  ;   MASM build rules
	  ;
	  build:macro ASM "MASM"
	  build:macro AFLAGS_G "/Mx /T"
	  build:macro AFLAGS_D "/Zi"
	  build:macro AFLAGS_R ""
	  build:inference .asm.obj as_asm_obj
	  build:release command as_asm_obj  \ 
	              "$(ASM) $(AFLAGS_G) $(AFLAGS_R) $<, $@;"
	  build:debug command as_asm_obj  \ 
	              "$(ASM) $(AFLAGS_G) $(AFLAGS_D) $<, $@;"
	  build:include .asm "^[ \t]*include[ \t]+\\([^ \t]+\\)"
	  build:include .inc "^[ \t]*include[ \t]+\\([^ \t]+\\)"
	
	These assembly flags can then be modified from PWB by using the following macros.
	The macros must be assigned to keystrokes to be activated. This can be done
	using the <ASSIGN> pseudo file. They can then be used to redefine the
	flags to pass to MASM.
	
	  ;
	  ;   MASM option-setting macros
	  ;
	  setAFG:= arg "Global MASM Options?"  prompt -> cancel lasttext home \ 
	          "build:macro AFLAGS_G \"" endline "\"" assign
	
	  setAFD:= arg "Debug MASM Options?"   prompt -> cancel lasttext home \ 
	          "build:macro AFLAGS_D \"" endline "\"" assign
	
	  setAFR:= arg "Release MASM Options?" prompt -> cancel lasttext home \ 
	          "build:macro AFLAGS_R \"" endline "\"" assign
	
	Additional query words: kbinf 1.10 PWBIss
	
	======================================================================
	Keywords          : kb16bitonly 
	Technology        : kbAudDeveloper kbPWBSearch kbZNotKeyword3 kbPWB110DOS kbPWB110OS2
	Version           : MS-DOS:1.1; OS/2:1.1
	
	=============================================================================
	

{% endraw %}
