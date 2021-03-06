---
layout: page
title: "Q151417: XCON: Latin-1 X.400 Bodypart Encoding Causes NDR"
permalink: /kb/151/Q151417/
---

## Q151417: XCON: Latin-1 X.400 Bodypart Encoding Causes NDR

{% raw %}

	Article: Q151417
	Product(s): Microsoft Exchange
	Version(s): winnt:4.0,5.0
	Operating System(s): 
	Keyword(s): kbusage
	Last Modified: 27-MAR-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, versions 4.0, 5.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	The use of ISO 8859-1 (Latin-1) as X.400 bodypart for the X.400 message text
	sent by Microsoft Exchange Server may result in this bodypart not being
	recognized by MTAs such as Digital's MAILbus 400. Therefore, no further
	processing, such as conversion can occur on this message. On the MAILbus 400
	side this may result in error message similar to the following:
	
	  Event:Converter Unavailable
	
	(Please see the More Information section for the complete error log). Eventually,
	a non-delivery report (NDR) will be sent back to Microsoft Exchange Server.
	
	CAUSE
	=====
	
	The encoding used by Microsoft Exchange Server for the ISO 8859-1 (Latin-1)
	bodypart lacks the escape sequence needed to invoke the G0 subset of the ISO
	Latin 1 character set.
	
	WORKAROUND
	==========
	
	Do not use the ISO 8859-1 (Latin-1) bodypart if the remote message transfer
	agent (MTA) is not able to decode the message without errors as sent by
	Microsoft Exchange Server.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft Exchange Server
	version 4.0. This problem has been corrected in the latest U.S. Service Pack for
	Microsoft Exchange Server version 4.0. For information on obtaining the Service
	Pack, query on the following word in the Microsoft Knowledge Base (without the
	spaces):
	
	  S E R V P A C K
	
	Microsoft has confirmed this to be a problem in Microsoft Exchange Server version
	5.0. This problem has been corrected in the latest U.S. Service Pack for
	Microsoft Exchange Server version 5.0. For information on obtaining the Service
	Pack, query on the following word in the Microsoft Knowledge Base (without the
	spaces):
	
	  S E R V P A C K
	
	MORE INFORMATION
	================
	
	Foreign MTAs may expect the ISO-8859-1 body part invoked, using four additional
	characters before the actual content (1b 28 42 0f). These four characters shall
	contain the escape sequence invoking the G0 subset of the ISO Latin 1 set.
	ISO/IEC 10021-7 Annex B, B.2 defines the General Text (extended) Bodypart. It
	refers to the G0 character set designators as follows:
	
	  The defaults for the G0 and C0 character set designators are those assumed as
	  designated and invoked by the ASN.1 Basic Encoding Rules (ISO 8825) for a
	  General String.
	
	The Latin-1 character set itself is defined in ISO 8859-1 and also defines the
	Escape sequences as follows: ISO 8859-1, 8 Designation of the character set
	
	  When required by other coding standards, for example ISO 2022 or ISO 4873,
	  the following pair of escape sequences shall be used: ESC 02/08 04/02 ESC
	  02/13 04/01 to designate the G0 and the G1 sets, respectively. According to
	  ISO 2022, the character SPACE does not require designation.
	
	ITU' s 1988 X series of recommendations also known as the Blue Book refer to
	these character set designators as follows: Rec. X.209, 23.5:
	
	  23.5 The octet string shall contain the octets specified in ISO 2022 for
	  encodings in an 8-bit environment, using the escape sequence and character
	  codings registered in accordance with ISO 2375. ..."
	
	The following is a sample of a resulting error as generated by Digital' s MAILbus
	400:
	
	  Event:Converter Unavailable
	        from:Node DEC:.abc.defgh MTA
	        at  :1996-12-13-14:49:07.851+01:00I-----
	
	        Converter Name                    = "latin1toiso6937"
	        Step                              = ""
	        Error Log                         =
	  "/var/mta/bad_msgs/latin1toiso69370008A832B15E"
	  Saved Bodypart                    =
	  "/var/mta/bad_msgs/isolatin10008A832B15E"
	  Message Identifier                =
	            [
	  Country = "CH" ,
	  Administration Domain = "400NET" ,
	  Private Domain = "PRMD" ,
	  Local Identifier = "ABCD-970113135033Z-8"
	            ]
	  Source                            =
	            [
	  Type = Domain ,
	  Domain Name = "DOM88"
	            ]
	  Originator                        = "C=CH; A@0NET; P_ABCD;
	  OU1=EXAB;OU2^; O=CDE; G=Abcd; S-efghijklmn;
	  /OrganizationName_A/OrganizationalUnit_BCDEFGH/CommonName=RECIPIENTS/Com
	  monName=AbcdB"
	  Error                             = Conversion Failed
	  # #Print the error log:
	  # more /var/mta/bad_msgs/latin1toiso69370008A832B15E
	  Input error - required character set not invoked prior to use
	  #
	
	MAILbus 400 is manufactured by Digital Equipment Corp., a vendor independent of
	Microsoft; we make no warranty, implied or otherwise, regarding this product's
	performance or reliability.
	
	
	Additional query words:
	
	======================================================================
	Keywords          : kbusage 
	Technology        : kbExchangeSearch kbExchange500 kbExchange400 kbZNotKeyword2
	Version           : winnt:4.0,5.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
