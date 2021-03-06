---
layout: page
title: "Q248370: Invoking COMTI Method Results in 1533 Exception Error"
permalink: /kb/248/Q248370/
---

## Q248370: Invoking COMTI Method Results in 1533 Exception Error

{% raw %}

	Article: Q248370
	Product(s): Microsoft SNA Server
	Version(s): WINDOWS:4.0 SP2,4.0 SP3
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft SNA Server, versions 4.0 SP2, 4.0 SP3 
	- Microsoft COM Transaction Integrator for CICS and IMS, versions 4.0 SP2, 4.0 SP3 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When an automation client attempts to call a COM Transaction Integrator for CICS
	and IMS (COMTI) method that contains a variable length ADO recordset nested in a
	user-defined type (UDT), An exception error occurs on completion of the method
	call. One of the following Windows NT events may be posted by COMTI to the
	Windows NT Application event log when this problem occurs:
	
	  (1533) An error occurred when attempting to read the actual size of
	  information for the safearray parameter RESPONSE_DATA in method CaseList.
	
	  (1564) An error occurred when attempting to acquire the allow variable length
	  property for parameter PARAMETER1 in method V100c.
	
	CAUSE
	=====
	
	COMTI does not properly handle recordsets that are nested in User Defined Types
	(UDTs).
	
	RESOLUTION
	==========
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem described in this article and should be applied only to
	systems experiencing this specific problem. This fix may receive additional
	testing at a later time, to further ensure product quality. Therefore, if you
	are not severely affected by this problem, Microsoft recommends that you wait
	for the next Microsoft SNA Server version 4.0 service pack that contains this
	fix.
	
	To resolve this problem immediately, contact Microsoft Product Support Services
	to obtain the fix. For a complete list of Microsoft Product Support Services
	phone numbers and information about support costs, please go to the following
	address on the World Wide Web:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	NOTE: In special cases, charges that are normally incurred for support calls may
	be canceled, if a Microsoft Support Professional determines that a specific
	update will resolve your problem. Normal support costs will apply to additional
	support questions and issues that do not qualify for the specific update in
	question.
	
	The English version of this fix should have the following file attributes or
	later:
	
	+--------------------------------+
	| File Name   | Date     | Time  | 
	+--------------------------------+
	| Convert.dll | xx/xx/xx | xx:xx | 
	+--------------------------------+
	
	NOTE: Date and time information will be provided as soon as it becomes
	available.
	
	
	NOTE: Because of file dependencies, the most recent fix that contains the above
	files may also contain additional files.
	
	
	
	WORKAROUND
	==========
	
	Replace nested recordsets with UDTs.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft SNA Server version
	4.0SP2 and 4.0SP3.
	
	MORE INFORMATION
	================
	
	The following IMS Cobol output area is a valid structure, which can be mapped to
	data-types represented in the COM world by using the Component Builder (CB) tool
	in COMTI. During the construction of the type library, the administrator will
	more than likely choose to represent the level 30 paragraph below with either a
	recordset or a UDT. If a recordset is used, COMTI throws an exception,
	considering that the recordset is nested in a UDT defined in paragraph 20 and
	10.
	
	  
	
	      01  GETCASELIST-OUTPUT-AREA.
	          05  LL                               PIC S9(4) COMP.
	          05  ZZ                               PIC S9(4) COMP.
	          05  RESPONSE-DATA.                                      
	     * USER DEFINED TYPE (CASE-LIST-RETURN)
	              10  CASE-LIST-RETURN.                               
	                  15  SCA-TRAN-SPACE      PIC X(11).              
	                  15  PFKEY               PIC X(2).               
	                  15  MODE-FIELD          PIC X.                  
	                  15  SCREEN-APPL         PIC X(4).               
	                  15  UPDATE-TASK         PIC X(4).               
	                  15  NEXT-GRDC-APPL      PIC X(4).               
	                  15  NEXT-GRDC-TASK      PIC X(4).               
	                  15  RETRIEVE-TASK       PIC X(4).               
	                  15  GRDC-TRAIN-IND      PIC X(5).               
	                  15  SAVE-MOD            PIC X(8).               
	                  15  TRAN-IND            PIC X.                  
	                  15  UPDATE-RETURN-CD    PIC X(4).               
	                  15  UPDT-SSN-KEY        PIC X(9).               
	                  15  UPDT-PAT-KEY        PIC X(2).               
	                  15  UPDT-CASE-ID        PIC X(9).               
	                  15  UPDT-AUTH-NO        PIC X(10).              
	                  15  UPDT-USER-ID        PIC X(5).               
	                  15  UPDT-CASE-SEQ       PIC X(3).               
	                  15  FILLER                   PIC X(17).              
	                  15  RETRIEVE-RETURN-CD  PIC X(4).               
	                  15  RETR-ERR-MSG        PIC X(55).              
	                  15  PA1-IND             PIC X.                  
	                  15  TICKLE-REFRESH-IND  PIC X.                  
	                  15  RETURN-DATA.                                
	     * USER DEFINED TYPE (CASE-LIST)
	                      20  CASE-LIST.                              
	                          25  NUM-OF-CASES                        
	                                               PIC 9(4) DISPLAY.
	                          25  CASES OCCURS 19 TIMES               
	                                        DEPENDING ON NUM-OF-CASES
	                                            OF GETCASELIST-OUTPUT-AREA.
	     * RECORDSET PROPERTIES (VARIABLE NUMBER OF ROWS).
	                              30  CASE-LIST.                           
	                               31  CASE-ID     PIC X(10).              
	                               31  STATUS      PIC X.                  
	                               31  PRIMARY-DX-TEXT                     
	                                               PIC X(30).
	                               31  CREATE-DT   PIC X(10).              
	                               31  ATT-PROV    PIC X(25).              
	                               31  CURRENT-OWNER                       
	                                               PIC X(5).
	                               31  CLOSE-DT    PIC X(10).              
	                  etc...
	        
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbSNAServSearch kbCOMTISearch kbCOMTI400SP2 kbCOMTI400SP3 kbSNAServ400SP2 kbSNAServ400SP3
	Version           : WINDOWS:4.0 SP2,4.0 SP3
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
