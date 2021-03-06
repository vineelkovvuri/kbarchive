---
layout: page
title: "Q223451: Multimedia Err Msg: OLE Initialization Failed..."
permalink: /kb/223/Q223451/
---

## Q223451: Multimedia Err Msg: OLE Initialization Failed...

{% raw %}

	Article: Q223451
	Product(s): Microsoft Home Multimedia Titles
	Version(s): WINDOWS:
	Operating System(s): 
	Keyword(s): kbenv kberrmsg kbinterop kbimu
	Last Modified: 06-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Encarta Encyclopedia 99 
	- Microsoft Encarta Reference Suite 99 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	After you install one of the programs listed at the beginning of this article on
	a Windows 95-based computer, when you attempt to start a different program, you
	may receive the following error message:
	
	  OLE initialization failed. Ensure that the OLE libraries are the correct
	  version.
	
	
	CAUSE
	=====
	
	The behavior can occur if the Object Linking and Embedding (OLE) library files
	installed in your computer are outdated.
	
	RESOLUTION
	==========
	
	To resolve this issue, install the updated OLE library files included with
	Encarta Encyclopedia 99, Encarta Reference Suite 99, or Encarta Virtual Globe
	99. To do this, follow these steps:
	
	1. Insert the Installation and Resources CD-ROM for the program into your CD-ROM
	  drive, or insert the Encarta Reference Suite 99 DVD-ROM into your DVD-ROM
	  drive. Press and hold down the SHIFT key when you insert the CD-ROM or
	  DVD-ROM to prevent the disc from starting automatically.
	
	2. Click Start, and then click Run.
	
	3. In the Open box, type the following line, and then click OK
	
	  <drive>:\Support
	
	  where <drive> is the drive letter of the CD-ROM drive.
	
	4. Double-click the Dcom95.exe file.
	
	5. Follow the instructions on the screen to finish installing the updated OLE
	  library files.
	
	MORE INFORMATION
	================
	
	The Dcom95.exe file installs the following files on your computer:
	
	  Filename       Size      Date       Time
	  ------------------------------------------
	
	  asycfilt.dll   147,728   06/02/98   06:24p
	  comcat.dll       6,144   06/18/98   11:25p
	  compobj.dll     31,152   06/18/98   11:24p
	  dcom2w98.dll     5,584   07/01/98   05:11p
	  dcom95.inf      12,122   07/13/98   02:23p
	  dcomdist.txt     2,634   07/02/98   10:42a
	  dllhost.exe     11,024   06/18/98   11:47p
	  imagehlp.dll   104,208   07/26/96   12:19p
	  install.exe     54,784   07/13/98   10:01a
	  iprop.dll       96,016   08/20/97   08:59p
	  license.txt     12,022   07/02/98   01:24p
	  ole2.dll        39,760   06/18/98   11:24p
	  ole32.dll      774,928   07/13/98   02:00p
	  oleaut32.dll   598,288   06/02/98   06:24p
	  olecnv32.dll    40,448   06/18/98   11:25p
	  olepro32.dll   164,112   06/02/98   06:24p
	  olethk32.dll    75,776   06/18/98   11:25p
	  relnotes.txt    32,152   07/02/98   03:57p
	  rpcltc1.dll      6,416   06/18/98   11:47p
	  rpcltc5.dll      7,440   06/18/98   11:47p
	  rpcltccm.dll    26,896   06/18/98   11:47p
	  rpclts5.dll      9,488   06/18/98   11:47p
	  rpcltscm.dll    20,240   06/18/98   11:47p
	  rpcmqcl.dll     12,560   06/18/98   11:47p
	  rpcmqsvr.dll    11,536   06/18/98   11:47p
	  rpcns4.dll      29,456   06/18/98   11:47p
	  rpcrt4.dll     320,784   06/18/98   11:46p
	  rpcss.exe        8,464   06/18/98   11:47p
	  secur32.dll     29,184   04/20/98   01:12p
	  stdole2.tlb     17,920   06/02/98   03:46p
	  stdole32.tlb     7,168   06/03/98   01:47p
	  storage.dll      4,224   06/18/98   11:24p
	
	Additional query words: multi media multi-media mmtitles mm enc99
	
	======================================================================
	Keywords          : kbenv kberrmsg kbinterop kbimu 
	Technology        : kbHomeProdSearch kbHomeMMsearch kbEncartaSearch kbEncartaEncycSearch kbEncartaEnCyc1999 kbEncartaReference99
	Version           : WINDOWS:
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
