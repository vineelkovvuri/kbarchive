---
layout: page
title: "Q104152: Multimedia Err Msg: Out-of-Date PICCLIP.VBX"
permalink: /kb/104/Q104152/
---

## Q104152: Multimedia Err Msg: Out-of-Date PICCLIP.VBX

{% raw %}

	Article: Q104152
	Product(s): Microsoft Home Multimedia Titles
	Version(s): 1.0,2.0
	Operating System(s): 
	Keyword(s): kbenv kberrmsg kbmm kbimukbfaq
	Last Modified: 09-NOV-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft 500 Nations, version 1.0 
	- Microsoft Ancient Lands for Windows, version 1.0 
	- Microsoft Art Gallery for Windows, version 1.0 
	- Microsoft Bookshelf for Windows, 1991, 1992, 1993, 1994, 1995 editions 
	- Microsoft Bookshelf '95 for Windows 95 
	- Microsoft Bookshelf 1996-97 for Windows 
	- Microsoft Cinemania for Windows, 1992, 1993, 1994, 1995, 1996, 1997 editions 
	- Microsoft Complete Baseball for Windows, 1994 edition (see below) 
	- Microsoft Complete Baseball Guide for Windows, 1995 edition 
	- Microsoft Complete Gardening for Windows, version 1.0 
	- Microsoft Complete NBA Basketball for Windows, 1994-1995, 1995-1996 editions 
	- Microsoft Dangerous Creatures for Windows, version 1.0 
	- Microsoft Dinosaurs for Windows, version 1.0 
	- Microsoft Dogs for Windows, version 1.0 
	- Microsoft Encarta 1994 The Complete Multimedia Encyclopedia 
	- Microsoft Encarta 95 The Complete Interactive Multimedia Encyclopedia for Macintosh 
	- Microsoft Encarta 96 Encyclopedia for Windows 
	- Microsoft Encarta 97 Encyclopedia for Windows 
	- Microsoft Encarta Encyclopedia 97 Deluxe for Windows 
	- Microsoft Encarta 96 World Atlas for Windows 
	- Microsoft Home CD Sampler 
	- Microsoft Isaac Asimov's The Ultimate Robot for Windows 
	- Microsoft Julia Child: Home Cooking with Master Chefs for Windows, version 1.0 
	- Microsoft Multimedia Mozart for Windows, version 1.0 
	- Microsoft Multimedia Schubert for Windows, version 1.0 
	- Microsoft Multimedia Strauss for Windows, version 1.0 
	- Microsoft Multimedia Stravinsky for Windows, version 1.0 
	- Microsoft Music Central for Windows, 1996, 1997 edition 
	- Microsoft Oceans for Windows, version 1.0 
	- Microsoft Reader's Digest Complete Do-It-Yourself Guide for Windows, version 1.0 
	- Microsoft Wine Guide for Windows, versions 1.0, 2.0 
	- Microsoft World of Flight for Windows, version 1.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you start one the programs listed at the top of this article, you may
	receive the following error message:
	
	  The file C:\WINDOWS\SYSTEM\PICCLIP.VBX is out of date.
	  This program requires a newer version.
	
	When you choose OK, the following error message appears:
	
	  Unexpected error: quitting.
	
	The program then closes.
	
	CAUSE
	=====
	
	This problem occurs if any of the three following conditions exist:
	
	- Another Visual Basic application is already running, and is using an
	  out-of-date version of the PICCLIP.VBX file.
	- An out-of-date version of the PICCLIP.VBX file is higher on the search list
	  than the current version installed with the applications listed at the top of
	  this article. The applications are finding the out-of-date version before
	  they get to the current version.
	- An out-of-date version of PICCLIP.VBX has copied over the version installed
	  by the Setup program for the applications listed at the top of this article.
	
	RESOLUTION
	==========
	
	NOTE: For more information about how to perform the steps listed below in
	Windows, see your Windows printed documentation or online Help.
	
	To correct the problem, copy the PICCLIP.VBX file again from your application
	CD-ROM to your Windows SYSTEM subdirectory, and remove all previous or duplicate
	versions of PICCLIP.VBX from your hard drive. The PICCLIP.VBX file is in the
	following locations:
	
	  SCHUBERT\MSSTP\SHARED (Schubert)
	  STRAUSS\MSSTP\SHARED (Strauss)
	  STRAV\MSSTP\SHARED (Stravinsky)
	  MOZART\MSSTP\SHARED (Mozart)
	  KIDSCAT (Magic School Bus)
	  ZZMMCAT (Baseball, Basketball)
	  SAMPLER (Sampler 4.0)
	  MMCAT (All Others)
	
	MORE INFORMATION
	================
	
	The programs listed at the top of this article search for the PICCLIP.VBX file
	in the following order (note that this follows standard Windows file search
	ordering):
	
	1. Current directory
	
	2. Windows directory
	
	3. Windows SYSTEM subdirectory
	
	4. All the directories on the path, in order
	
	The Setup program installs PICCLIP.VBX to the Windows SYSTEM directory. If the
	applications listed at the top of this article encounter an invalid version of
	PICCLIP.VBX before they find the up-to-date version, the error occurs. Problems
	may also occur if more than one copy of the PICCLIP.VBX file is found.
	
	Additional query words: old recent kbmm Dev/Drv mmtitles writer artist msb explora money
	
	======================================================================
	Keywords          : kbenv kberrmsg kbmm kbimu kbfaq
	Technology        : kbHWMAC kbOSMAC kbHomeProdSearch kbHomeMMsearch kbEncartaSearch kbGamesSearch kbZNotKeyword kbKidsSearch kbBookshelfSearch kbBaseballSearch kbEncartaEncycSearch kbCineManiaSearch kbZNotKeyword5 kbAncientLands kbCompleteBaseballSearch kbCompleteBasketballSearch kbMMStrauss kbMMSchubert kbMMStravinsky kbMMMozart100 kb500Nations100 kbAsimovSearch kbBookShelf1995 kbBookShelf1996 kbBookShelf1997 kbCompleteBaseball1994 kbCompleteBaseball1995 kbCompleteGardening kbDangerousCreatures kbDinosaurs100 kbDogs100 kbAsimovUltimateRobot kbJuliaChild kbMusicCentral kbWine100 kbWine200 kbWorldofFlight kbArtGallery kbCompleteNBABasketball1994 kbEncartaEnCyc1996 kbEncartaEnCyc1997 kbEncartaEnCyc1997Del kbEncartaEnCyc1994 kbEncartaEnCyc1995Mac kbEncartaWorldAtlas1996 kbMusicCentral1996 kbMusicCentral1997 kbOceans kbDoItYourself
	Version           : :1.0,2.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
