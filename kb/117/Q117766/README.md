---
layout: page
title: "Q117766: Playing Compressed Audio on a Audio Plus Sound Card"
permalink: /kb/117/Q117766/
---

## Q117766: Playing Compressed Audio on a Audio Plus Sound Card

{% raw %}

	Article: Q117766
	Product(s): Microsoft Home Multimedia Titles
	Version(s): WINDOWS:1.0,2.0; :1.0,1993 edition,1994 edition,1995 edition
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-NOV-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Ancient Lands for Windows, version 1.0 
	- Microsoft Art Gallery for Windows, version 1.0 
	- Microsoft Bookshelf for Windows versions 1993 edition, 1994 edition, 1995 edition 
	- Microsoft Bookshelf '95 for Windows 95 
	- Microsoft Bookshelf 1996-97 for Windows 
	- Microsoft Cinemania for Windows 1994 edition 
	- Microsoft Complete Baseball for Windows, version 1994 edition 
	- Microsoft Creative Writer for Windows, version 1.0 
	- Microsoft Dangerous Creatures for Windows, version 1.0 
	- Microsoft Dinosaurs for Windows, version 1.0 
	- Microsoft Encarta 1994 The Complete Multimedia Encyclopedia 
	- Microsoft Encarta 95 The Complete Interactive Multimedia Encyclopedia for Macintosh 
	- Microsoft Encarta 96 Encyclopedia for Windows 
	- Microsoft Fine Artist for Windows, version 1.0 
	- Microsoft Multimedia Mozart for Windows, version 1.0 
	- Microsoft Multimedia Schubert for Windows, version 1.0 
	- Microsoft Multimedia Stravinsky for Windows, version 1.0 
	- Microsoft Multimedia Strauss for Windows, version 1.0 
	- Microsoft Musical Instruments for Windows, version 1.0 
	- Microsoft SoundBits (all collections), version 1.0 
	- Microsoft Wine Guide for Windows, versions 1.0, 2.0 
	-------------------------------------------------------------------------------
	
	
	SUMMARY
	=======
	
	Audio Plus and Audio Plus II cards, by Zoltrix, support compressed audio, when
	they are configured to use the SoundBlaster drivers.
	
	MORE INFORMATION
	================
	
	The above mentioned applications use the Microsoft Audio Compression Manager to
	produce sounds.
	
	To install the SoundBlaster driver, use the driver disk that accompanies the
	Audio Plus or Audio Plus II card. This includes the SNDBLST2.DRV file.
	
	You will need to edit the SYSTEM.INI file; it can be opened in any text editor,
	such as the Windows Notepad or the MS-DOS Editor.
	
	Below are sections of the SYSTEM.INI file that include the setup for the sound
	card. The port (I/O Base Address), INT (interrupt/IRQ), and DMACHANNEL (DMA
	channel) settings may be different, depending on the settings on the sound
	card.
	
	  [Drivers]
	     MIDI=apdev.drv
	     Wave=apdev.drv
	     MIDI1=apmus.drv
	
	     [apdev.drv]
	     port=220
	     int=7
	     dmachannel=1
	
	     [apmus.drv]
	     port=220
	
	The Zoltrix 16 cards will play compressed audio if you edit the above sections of
	the SYSTEM.INI file to look like the entries listed below. You may have to add
	the [sndblst2.drv] and [MSACM] sections. A semicolon (;) in the SYSTEM.INI file
	indicates that the line is a comment and the information will not load into
	memory.
	
	     [Drivers]
	     ;MIDI=apdev.drv
	     ;Wave=apdev.drv
	     ;MIDI1=apmus.drv
	     Wave1=sndblst2.drv
	     MIDI2=sndblst2.drv
	
	     ;[apdev.drv]
	     ;port=220
	     ;int=7
	     ;dmachannel=1
	
	     ;[apmus.drv]
	     ;port=220
	
	     [sndblst2.drv]
	     port=220
	     int=7
	
	The products included here are manufactured by vendors independent of Microsoft;
	we make no warranty, implied or otherwise, regarding these products' performance
	or reliability.
	
	Support for the Zoltrix sound cards is provided by the following companies:
	
	In the United States, support is provided by the manufacturer, Zoltrix:
	
	  Main telephone number: (510) 657-1188
	  Technical support number: (510) 657-5737
	
	In Canada, support is provide by the distributor, 3D MicroComputers:
	
	  Main telephone number: (905) 479-8822
	  Service number: (905) 479-3668
	  Tech. Support number: (800) 846-7655
	
	Additional query words: kbhowto zoltrix soundblaster sb sbpro pro creative labs zoltric zoltrick zoltrik mm wm_writer wm_artist sound bits clips sound-
	
	======================================================================
	Keywords          :  
	Technology        : kbHWMAC kbOSMAC kbHomeProdSearch _IKkbbogus kbHomeMMsearch kbEncartaSearch kbGamesSearch kbZNotKeyword kbZNotKeyword2 kbBookshelfSearch kbSoundBitsSearch kbBaseballSearch kbEncartaEncycSearch kbCineManiaSearch kbAncientLands kbCompleteBaseballSearch kbCreativeWriter100 kbMMStrauss kbMMSchubert kbMMStravinsky kbMMMozart100 kbBookShelf1993 kbBookShelf1994 kbBookShelf1995 kbBookShelf1996 kbBookShelf1997 kbCinemania1994 kbCompleteBaseball1994 kbDangerousCreatures kbDinosaurs100 kbFineArtist100 kbMusicalInst kbSoundBits kbWine100 kbWine200 kbArtGallery kbEncartaEnCyc1996 kbEncartaEnCyc1994 kbEncartaEnCyc1995Mac
	Version           : WINDOWS:1.0,2.0; :1.0,1993 edition,1994 edition,1995 edition
	
	=============================================================================
	

{% endraw %}
