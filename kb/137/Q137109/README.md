---
layout: page
title: "Q137109: Algorithm Used to Accept Requests from SNA Devices"
permalink: /kb/137/Q137109/
---

## Q137109: Algorithm Used to Accept Requests from SNA Devices

{% raw %}

	Article: Q137109
	Product(s): Microsoft SNA Server
	Version(s): WINDOWS:2.0,2.1,2.11,3.0,4.0
	Operating System(s): 
	Keyword(s): kbinterop kbnetwork kbsetup sna4
	Last Modified: 12-JUN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft SNA Server, versions 2.0, 2.1, 2.11, 3.0, 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article explains how SNA Server uses identifying information (XIDs) from
	incoming calls to help you decide which kind of remote node identifier to
	specify for a connection that accepts incoming calls.
	
	MORE INFORMATION
	================
	
	When SNA Server receives an XID from an incoming call such as a DSPU, host, or
	AS/400, for instance, it looks at the XID for some kind of identifier of the
	remote system that made the call. It compares this identifier, in the order
	shown in the following list, against identifiers stored in the SNA Server
	configuration. If it finds a match, it accepts the call. If it finds that
	identifiers are left unspecified (in the configuration and/or the XID), and the
	connection is an SDLC connection, SNA Server accepts the call, pending further
	exchange of information. In other cases, if every comparison yields a mismatch,
	or when identifiers are left unspecified and the connection is 802.2 or X.25,
	SNA Server rejects the incoming call.
	
	Identifiers are compared in the following order:
	
	1. If the incoming XID is Format 3, SNA Server examines the XID for a remote
	  node Network Name and Control Point Name. If these parameters are present in
	  both the incoming XID and in the SNA Server configuration, and they match,
	  the call is accepted. If the parameters are present and do not match, the
	  call is rejected.
	
	2. If the parameters are not available for the preceding step, Remote Node IDs
	  are examined next. Remote Node IDs may be used in either Format 0 or Format 3
	  XIDs. If a Remote Node ID is present in both the incoming XID and in the SNA
	  Server configuration, and they match, the call is accepted. If the parameters
	  are present and do not match, the call is rejected.
	
	3. If the parameters were not available for the preceding steps, for 802.2 and
	  X.25 connections, remote addresses are examined:
	   - For 802.2 connections, the Remote Network Address in the SNA Server
	     configuration is compared to the address from which the XID was received.
	     If the addresses match, the call is accepted; if not, the call is
	     rejected.
	
	     NOTE: SNA Server 2.11 has a new feature that allows any client to attach to
	     SNA Server regardless of an XID or remote network address match. To do
	     this, configure the downstream connection's remote network address to be:
	     400000000000.
	
	   - For X.25 connections, the remote X.25 address in the SNA Server
	     configuration is compared to the address from which the XID was received.
	     If the addresses match, the call is accepted; if not, the call is
	     rejected.
	
	4. If no match is found in any of the preceding steps:
	   - For 802.2 and X.25 connections the incoming call is rejected.
	
	   - For SDLC connections, if identifiers were left unspecified in the
	     configuration and/or the XID, the call is accepted, pending further
	     exchange of identifiers. However, if identifiers were not left unspecified
	     and no identifiers match, the call is rejected.
	
	To Enable Incoming Calls for a Specific Connection
	--------------------------------------------------
	
	For 2.11:
	
	1. In SNA Server Admin, go to Connection Properties for the specific connection.
	
	2. Select Allowed Directions: Incoming Calls.
	
	For 3.0:
	
	1. In SNA Server Manager, go to the properties page of the connection in
	  question.
	
	2. In the General tab, select Allowed Directions: Incoming Calls.
	
	Additional query words: prodsna
	
	======================================================================
	Keywords          : kbinterop kbnetwork kbsetup sna4 
	Technology        : kbAudDeveloper kbSNAServSearch kbSNAServ300 kbSNAServ200 kbSNAServ211 kbSNAServ400 kbSNAServ210
	Version           : WINDOWS:2.0,2.1,2.11,3.0,4.0
	
	=============================================================================
	

{% endraw %}
