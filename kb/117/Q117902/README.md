---
layout: page
title: "Q117902: FIX: D2030 Internal Compiler Error with /Ox"
permalink: /kb/117/Q117902/
---

## Q117902: FIX: D2030 Internal Compiler Error with /Ox

{% raw %}

	Article: Q117902
	Product(s): Microsoft Fortran Compiler
	Version(s): 1.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 24-MAR-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft FORTRAN PowerStation for MS-DOS, version 1.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	The following error message is generated when the sample code below is compiled
	for MS-DOS using option /Ox:
	
	  Command line error D2030 : INTERNAL COMPILER ERROR
	
	RESOLUTION
	==========
	
	Compile the code from an MS-DOS command prompt under Windows.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a bug in FORTRAN PowerStation for MS-DOS,
	version 1.0. This problem was corrected in the FORTRAN PowerStation for MS-DOS
	maintenance release, version 1.0a.
	
	MORE INFORMATION
	================
	
	FORTRAN PowerStation, version 1.0, can be differentiated from the maintenance
	release, version 1.0a, by invoking the linker. Typing "link32 | more" (without
	the quotation marks) from the \F32\BIN directory will show version 2.8 for
	FORTRAN PowerStation, version 1.0, and will show version 1.0f for the
	maintenance release, version 1.0a.
	
	The following sample code illustrates this problem:
	
	Sample Code
	-----------
	
	  C compile options required: /Ox
	
	        COMMON/FLOWED/QCURVE(1,3,26),NATUR
	        DIMENSION DUMMYS(3,26)
	   1800 IF(QCURVE(NATUR,2,I).GE.AA) THEN
	          DUMMYS(3,K) = QCURVE(NATUR,3,I-1)
	          IF(K.EQ.26) GO TO 1810
	        ELSE
	          I  = I + 1
	        ENDIF
	        GO TO 1800
	   1810 DO 1850 I = 2,25
	   1850   QCURVE(NATUR,3,I) = DUMMYS(3,I)
	        END
	
	Additional query words: 1.00 buglist1.00 fixlist1.00a
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbFortranSearch kbZNotKeyword3 kbFORTRANPower100DOS
	Version           : :1.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
