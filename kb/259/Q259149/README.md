---
layout: page
title: "Q259149: SNA Server Selects Bad Dependent APPC LU from Default Pool"
permalink: /kb/259/Q259149/
---

## Q259149: SNA Server Selects Bad Dependent APPC LU from Default Pool

{% raw %}

	Article: Q259149
	Product(s): Microsoft SNA Server
	Version(s): WINDOWS:4.0,4.0 SP1,4.0 SP2,4.0 SP3
	Operating System(s): 
	Keyword(s): kbSNA400sp4fix kbSNA400PreSP4fix
	Last Modified: 08-DEC-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft SNA Server, versions 4.0, 4.0 SP1, 4.0 SP2, 4.0 SP3 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If multiple dependent local APPC LUs are configured with the Member of default
	outgoing local APPC LU pool check box enabled, and an APPC or CPIC application
	specifies a blank Local LU alias when it attempts to allocate a conversation to
	a Remote APPC LU, the SNA Server computer may fail to locate an available local
	LU and reject the Allocate request. When this occurs, the SNA Server computer
	selects a local LU that is already being used, instead of choosing an available
	local APPC LU in the pool.
	
	If this occurs with an APPC application, the [MC_]ALLOCATE fails with the
	following error message:
	
	  primary_rc = 0x0003 (AP_ALLOCATION_ERROR)
	  secondary_rc = 0x00000005 (AP_ALLOCATION_FAILURE_RETRY)
	
	A CPIC application fails with the following error message:
	
	  rc = 20 (CM_PRODUCT_SPECIFIC_ERROR)
	
	This problem can occur when the dependent local APPC LU pool is used to access a
	single Remote APPC LU, or multiple Remote APPC LUs.
	
	NOTE: There are other causes for these failures other that this specific problem.
	For example, if the host rejects the INITSELF request to activate a session, or
	there is a problem with the connection, these error messages may also occur.
	
	Also, when the Default pool check box is selected on a local APPC LU, the LU may
	be used to access any remote APPC LU if a blank local LU alias is provided by
	the APPC application. Therefore, the remote APPC LU (on the remote system) must
	be enabled to support sessions from any pooled local APPC LU.
	
	CAUSE
	=====
	
	When opening a pooled-dependent local APPC LU, the SNA Server incorrectly
	selects an LU that
	
	- has not fully completed the session activation process due to an allocate
	  request by a different user (for example, waiting for an LUSTAT reply)
	
	- is already in session with a different Remote APPC LU
	
	- has been deactivated by a DACTLU command and has not received a new ACTLU
	
	RESOLUTION
	==========
	
	To resolve this problem, obtain the latest service pack for SNA Server 4.0. For
	additional information, click the following article number to view the article
	in the Microsoft Knowledge Base:
	
	  Q215838 How to Obtain the Latest SNA Server Version 4.0 Service Pack
	
	
	
	STATUS
	======
	
	Microsoft has confirmed that this is a problem in Microsoft SNA Server version
	4.0, 4.0 SP1, 4.0 SP2 and 4.0 SP3.
	
	This problem was first corrected in SNA Server 4.0 Service Pack 4.
	
	
	Additional query words:
	
	======================================================================
	Keywords          : kbSNA400sp4fix kbSNA400PreSP4fix 
	Technology        : kbAudDeveloper kbSNAServSearch kbSNAServ400 kbSNAServ400SP1 kbSNAServ400SP2 kbSNAServ400SP3
	Version           : WINDOWS:4.0,4.0 SP1,4.0 SP2,4.0 SP3
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
