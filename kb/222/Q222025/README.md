---
layout: page
title: "Q222025: Attachmate Advanced ISCA Adapter General Information"
permalink: /kb/222/Q222025/
---

## Q222025: Attachmate Advanced ISCA Adapter General Information

{% raw %}

	Article: Q222025
	Product(s): Microsoft SNA Server
	Version(s): WINDOWS:2.11SP1,2.11SP2,3.0,3.0SP1,3.0SP2,3.0SP3,4.0,4.0SP1,4.0SP2
	Operating System(s): 
	Keyword(s): 
	Last Modified: 13-MAR-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft SNA Server, versions 2.11SP1, 2.11SP2, 3.0, 3.0SP1, 3.0SP2, 3.0SP3, 4.0, 4.0SP1, 4.0SP2 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article outlines configuration and use of the Attachmate Advanced ISCA PNP
	(Plug and Play) and Advanced ISCA PCI SDLC Adapters.
	
	The Advanced ISCA Plug and Play ISA Adapter 
	-------------------------------------------
	
	The Advanced ISCA Plug and Play Adapter is an ISA Plug and Play adapter. It may
	be configured in Legacy mode, meaning it will not participate in Plug and Play
	enumeration, and can be "hard coded" with IRQ, I/O, and memory range, or it can
	be configured in Plug and Play mode in which the resources are assigned by the
	Plug and Play BIOS extensions.
	
	Plug and Play mode may require the use of the PNPISA driver in Windows NT 4.0.
	The configuration is accomplished by either an MS-DOS-based or a Windows
	NT-based diagnostic program. The MS-DOS diagnostic is Iscapnp.exe and the
	Windows NT diagnostic is AdvIscaDiagNT. The Windows NT diagnostic is installed
	using the supplied Setup program. The link service is installed into SNA Server
	in the same manner, using a Setup program. If the adapter is in Legacy mode, you
	should install the link service by selecting External Link Service on the Tools
	menu. If in Plug and Play mode, on the Insert menu, select Link Service.
	
	The driver is Adisync.sys coupled with Ibmsdlc.dll providing the link layer, and
	is designed to support up to three adapters in a server. The link service is
	ADISDLC#.
	
	The Advanced ISCA PCI Adapter
	-----------------------------
	
	The Advanced ISCA PCI Adapter is a PCI version 2.1 compliant adapter. Its
	resources are assigned by the BIOS and, depending upon the BIOS and PCI chipset
	in use, may be changed through the BIOS or diagnostics. The diagnostic is
	IscaDiagNT and is Windows NT-based. It is installed by running Setup from the
	installation disk set or the downloaded file. The link service is also installed
	using a Setup routine and is reported in Add/Remove Programs in Control Panel.
	It is also removed using Add/Remove Programs.
	
	The diagnostic will report a "board not found" message if the SNA Server link
	service using the adapter is active. The link service will also not become
	active if the diagnostic is active.
	
	The driver is Adpsync.sys coupled with Ibmsdlc.dll, and is designed to support up
	to three adapters. The link service is ADPSDLC#.
	
	Both adapters use a special 26-pin cable, which is an RS-232 alternate. The
	additional pin is used for digital versus analog circuit detection. They are
	rated at 512 KB by Attachmate.
	
	REFERENCES
	==========
	
	Attachmate Technical Bulletins 167, 173. PCI specification
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbSNAServSearch kbSNAServ300 kbSNAServ400
	Version           : WINDOWS:2.11SP1,2.11SP2,3.0,3.0SP1,3.0SP2,3.0SP3,4.0,4.0SP1,4.0SP2
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
