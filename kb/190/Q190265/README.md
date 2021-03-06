---
layout: page
title: "Q190265: HOWTO: Find the Day that Daylight Savings Time Occurs"
permalink: /kb/190/Q190265/
---

## Q190265: HOWTO: Find the Day that Daylight Savings Time Occurs

{% raw %}

	Article: Q190265
	Product(s): Microsoft FoxPro
	Version(s): MACINTOSH:2.5b,2.5c,2.6a,3.0; WINDOWS:2.5,2.5a,2.5b,2.6,2.6a,3.0,3.0b,5.0,5.0a,6.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 02-MAY-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 3.0, 3.0b, 5.0, 5.0a, 6.0 
	- Microsoft FoxPro for Windows, versions 2.5, 2.5a, 2.5b, 2.6, 2.6a 
	- Microsoft FoxPro for Macintosh, versions 2.5b, 2.5c, 2.6a 
	- Microsoft Visual FoxPro for Macintosh, Professional Edition, version 3.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Under legislation enacted in 1986, Daylight Savings time in the United States
	(U.S.) begins at 2 A.M. on the first Sunday of April and ends at 2 A.M. on the
	last Sunday of October. The sample code in the MORE INFORMATION section
	determines what day in April the first Sunday occurs and on and what day in
	October the last Sunday occurs for each year.
	
	MORE INFORMATION
	================
	
	Sample Code
	-----------
	
	     * Note that bdate and edate are assigned the first day of April and the
	     * last day of October in this example. You would want to change these
	     * variables to be equal to the DATE() function in a real situation.
	
	        CLEAR
	
	        IF "6.00"$VERSION(1)
	           oldstrictdate = SET("STRICTDATE")
	           SET STRICTDATE TO 0
	        ENDIF
	
	        bdate = {04/01/98}  && Change year to check other dates,
	        edate = {10/31/98}  && use the DATE() function for real time.
	        y = ""
	        IF MONTH(bdate) = 4 AND DAY(bdate) < 8  && First week of April.
	           * Need first day of month and current year, change to DATE().
	           bsavings = CTOD('04/01/' + ALLTRIM(STR(YEAR(BDATE))))
	          =getnum(CDOW(bsavings)) && Get number to add to first day of April.
	           ? "Daylight Savings Time starts on Sunday - "
	           ?? bsavings + VAL(SUBSTR(y,1,1))
	           ? "The first day of April is: "
	           ?? CDOW(bsavings)
	        ENDIF
	
	        IF MONTH(edate) = 10 AND DAY(edate) > 24  && Last week of October.
	           * Need last day of month and current year, change to DATE().
	           esavings = CTOD('10/31/' + ALLTRIM(STR(YEAR(EDATE))))
	           =getnum(CDOW(esavings))  && Get number to subtract from 10/31.
	           ? "Daylight Savings Time ends on Sunday - "
	           ?? esavings - VAL(SUBSTR(y,2,1))
	           ? "The last day of October is: "
	           ?? CDOW(esavings)
	        ENDIF
	
	        IF "6.00"$VERSION(1)
	           SET STRICTDATE TO &oldstrictdate
	        ENDIF
	
	        PROCEDURE getnum
	        PARAMETER dayvar
	
	        DO CASE
	           CASE dayvar = "Sunday"
	           y='00'
	           CASE dayvar = "Monday"
	           y='61'
	           CASE dayvar = "Tuesday"
	           y='52'
	           CASE dayvar = "Wednesday"
	           y='43'
	           CASE dayvar = "Thursday"
	           y='34'
	           CASE dayvar = "Friday"
	           y='25'
	           CASE dayvar = "Saturday"
	           y='16'
	        ENDCASE
	
	     ********************* End of code *******************
	
	Additional query words: kbvfp600
	
	======================================================================
	Keywords          :  
	Technology        : kbHWMAC kbOSMAC kbVFPsearch kbAudDeveloper kbFoxproSearch kbFoxPro250bMac kbFoxPro260aMac kbFoxPro250cMac kbFoxPro260 kbFoxPro250 kbFoxPro250a kbFoxPro250b kbFoxPro260a kbVFP300Mac kbVFP300 kbVFP300b kbVFP500 kbVFP600 kbVFP500a
	Version           : MACINTOSH:2.5b,2.5c,2.6a,3.0; WINDOWS:2.5,2.5a,2.5b,2.6,2.6a,3.0,3.0b,5.0,5.0a,6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
