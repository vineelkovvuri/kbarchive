---
layout: page
title: "Q142538: PRB: M6110 Run-Time Error Occurs When Using SYSTEMQQ or RUNQQ"
permalink: /kb/142/Q142538/
---

## Q142538: PRB: M6110 Run-Time Error Occurs When Using SYSTEMQQ or RUNQQ

{% raw %}

	Article: Q142538
	Product(s): Microsoft Fortran Compiler
	Version(s): 1.0,1.0a,4.0
	Operating System(s): 
	Keyword(s): kbFortranPS kbLangFortran
	Last Modified: 04-MAY-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft FORTRAN PowerStation for MS-DOS, versions 1.0, 1.0a 
	- Microsoft Fortran Powerstation 32 for Windows NT, version 1.0 
	- Microsoft Fortran Powerstation 32 for Windows NT, version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	An application that uses either the SYSTEMQQ or RUNQQ run-time functions without
	specifying the proper include files causes this run-time error:
	
	  run-time error: M6110 MATH
	  - floating-point error: stack overflow
	
	CAUSE
	=====
	
	The definitions for the SYSTEMQQ and RUNQQ functions are not found and are
	incorrectly interpreted by the compiler. The definitions of the two functions
	are located in the Flib.fi and Flib.fd include files under Microsoft FORTRAN
	PowerStation versions 1.0 and 1.0a for MS-DOS and Microsoft FORTRAN PowerStation
	32 version 1.0 for Windows NT. If you are using Microsoft FORTRAN PowerStation
	32 version 4.0, the function definitions are located in the MSFLIB module.
	
	RESOLUTION
	==========
	
	When using Microsoft FORTRAN PowerStation versions 1.0 and 1.0a for MS-DOS or
	Microsoft FORTRAN PowerStation 32 version 1.0 for Windows NT, specify the
	Flib.fi and Flib.fd include files in the appropriate places. Under Microsoft
	FORTRAN PowerStation 32 version 4.0, place the "USE MSFLIB" statement at the
	beginning of the program unit that references either of these functions.
	
	STATUS
	======
	
	This behavior is by design.
	
	MORE INFORMATION
	================
	
	Sample Code Demonstrating Behavior
	----------------------------------
	
	  C  Compile options needed: none
	
	  C  Running the code below causes the M6110 run-time error.
	        nResult = SYSTEMQQ("DIR")
	        END
	
	Sample Code Demonstrating Solution
	----------------------------------
	
	The following code demonstrates the solution using Microsoft PowerStation
	versions 1.0 and 1.0a for MS-DOS and Microsoft PowerStation 32 version 1.0 for
	Windows NT.
	
	  C Compile options needed: none
	
	  C The proper include files are specified and correctly referenced
	        INCLUDE "FLIB.FI"
	        INCLUDE "FLIB.FD"
	        LOGICAL nResult
	        nResult = SYSTEMQQ("DIR")
	        END
	
	Sample Code Demonstrating Solution for FORTRAN PowerStation 32 4.0
	------------------------------------------------------------------
	
	Under Microsoft FORTRAN PowerStation 32 version 4.0 using the statement "USE
	MSFLIB" causes the "SYSTEMQQ" function definition to be referenced correctly.
	The following code illustrates this:
	
	  C Compile options needed: none
	        USE MSFLIB   ! Commenting this line causes the run-time error
	        LOGICAL nResult
	        nResult = SYSTEMQQ("DIR")
	        END
	
	Additional query words: 1.00 1.00a 4.00
	
	======================================================================
	Keywords          : kbFortranPS kbLangFortran 
	Technology        : kbAudDeveloper kbFortranSearch kbZNotKeyword2 kbZNotKeyword3 kbFORTRANPower32100NT kbFORTRANPower32400NT kbFORTRANPower100DOS kbFORTRANPower100aDOS
	Version           : :1.0,1.0a,4.0
	
	=============================================================================
	

{% endraw %}
