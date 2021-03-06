---
layout: page
title: "Q154728: Close Combat: Playing Over a Network"
permalink: /kb/154/Q154728/
---

## Q154728: Close Combat: Playing Over a Network

{% raw %}

	Article: Q154728
	Product(s): Microsoft Home Games
	Version(s): 1.0
	Operating System(s): 
	Keyword(s): kbmm kbusagekbfaq
	Last Modified: 19-FEB-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Close Combat for Windows 1.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article discusses how to play Close Combat over a Local or Wide Area
	Network (LAN or WAN).
	
	SYSTEM CONFIGURATION
	--------------------
	
	To begin, make sure your system is configured correctly, as follows:
	
	1. Check to make sure TCP/IP is loaded as a protocol for the Network adapter
	  card, as follows:
	
	  a. Click the Start button, point to Settings, and click Control Panel.
	
	  b. Click Network.
	
	  c. Click the Configuration tab. If TCP/IP is not listed, click Add and follow
	     the dialog boxes.
	
	2. Disable the TCP/IP - Dial-Up Adapter protocol, as follows:
	
	  a. Click the Start button, point to Settings, then click Control Panel.
	
	  b. Double click System, and choose the Device Manager tab.
	
	  c. Click the (Plus) sign next to Network Adapters.
	
	  d. Click Dial-up Adapter, and press Properties.
	
	  e. Under Device Usage, clear the Original Configuration box.
	
	(Dial-Up Networking is dynamic, so re-starting Windows is not necessary.)
	3. Determine both IP Addresses. One player needs to know both. To determine your
	  IP address, start the game and press the 2 Player option button on the
	  Command screen. Your IP address should be listed.
	
	STARTING THE GAME
	-----------------
	
	1. Both players need to start Close Combat, and press the 2 Player option button
	  on the Command screen.
	
	2. Player 1 (the player that has a list of both IP Addresses) needs to click
	  Initiate Connection, enter the opponents IP Address in the space provided,
	  and click OK.
	
	3. Player 2 needs to click Wait For Connection and then press OK.
	
	  Dial-Up Networking binds to the TCP/IP protocol last and therefore is the
	  default. When player 2 clicks Wait For Connection, Close Combat looks to the
	  Dial-Up Networking protocol, if present, regardless of the chosen IP Address.
	
	Once both players hear the Artificial Entity announce "Connection Established,"
	they can then press Begin to start the game.
	
	MORE INFORMATION
	================
	
	
	To play a game modem to modem, see the following article in the Microsoft
	Knowledge Base:
	
	  Q154729 Close Combat: Modem Play Using Dial-up Networking
	
	To play a game over the Internet, see the following article in the Microsoft
	Knowledge Base:
	
	  Q154727 Close Combat: Playing Over the Internet
	
	Additional query words: 1.00 1.10 close combat network connection
	
	======================================================================
	Keywords          : kbmm kbusage kbfaq
	Technology        : kbHomeProdSearch kbGamesSearch kbZNotKeyword kbCloseCombatSearch kbCloseCombat
	Version           : :1.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
