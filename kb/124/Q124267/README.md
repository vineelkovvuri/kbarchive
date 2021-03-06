---
layout: page
title: "Q124267: Display Adapter Information and Useful Switches"
permalink: /kb/124/Q124267/
---

## Q124267: Display Adapter Information and Useful Switches

{% raw %}

	Article: Q124267
	Product(s): Microsoft Windows 95.x Retail Product
	Version(s): Win2000:95
	Operating System(s): 
	Keyword(s): win95
	Last Modified: 17-DEC-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows 95 
	-------------------------------------------------------------------------------
	
	
	SUMMARY
	=======
	
	This article describes switches that correct some display problems that can
	occur in Microsoft Windows 95.
	
	MORE INFORMATION
	================
	
	The [boot] section of the SYSTEM.INI file should contain the following line for
	any Windows 95 version of a display driver:
	
	  DISPLAY.DRV=PNPDRVR.DRV
	
	The actual video driver (such as VGA.DRV or S3.DRV) is loaded from the registry.
	This allows support for dockable personal computers that have different adapters
	for the laptop versus the docking station.
	
	Setting the monitor type in the display properties does not affect the refresh
	rate output by your display adapter. To change this, you must run a utility
	supplied by your display adapter manufacturer or computer manufacturer. Some
	display utilities must be run in the AUTOEXEC.BAT file; however, on other
	computers, display type is set in BIOS configuration programs.
	
	Examples of display utilities from adapter manufacturers include the following:
	
	  ATI                      INSTALL.EXE
	  Cirrus Logic             MONTYPE.EXE, CLMODE.EXE
	  Diamond Stealth          STLMODE.EXE
	  Tseng Labs               VMODE.EXE
	  Western Digital          VGAMODE.EXE
	
	The sections below describe different video cards and the requirements for these
	drivers to work correctly in Windows 95.
	
	ATI Mach 8/32/64
	----------------
	
	This adapter must be configured correctly using the ATI INSTALL.EXE program for
	Windows 95 to use high-resolution modes properly. Correct setting of your
	monitor type is especially important. This is because the high- resolution modes
	may not be available for selection, or the computer may fail when attempting to
	switch to that mode.
	
	Compaq QVision 2000
	-------------------
	
	These adapters use the Matrox MGA controller.
	
	Matrox MGA
	----------
	
	These adapters are supported with Windows 95 drivers. The VGA driver is installed
	by Setup.
	
	Diamond Stealth 64
	------------------
	
	For True Color support (16.7 million colors) add TrueColor=24 in the [DISPLAY]
	section of the SYSTEM.INI
	
	Diamond Viper
	-------------
	
	Setup preserves Microsoft Windows 3.1 drivers for this adapter when Setup is run
	from within Windows 3.1. Setting up Windows 95 from MS-DOS causes the Windows 95
	VGA driver to be installed. If this occurs, the Diamond Viper setup program
	should be used to install the Windows 3.1 drivers into Windows 95. Copy the
	latest Viper files from the Drivers directory on the Windows 95 CD.
	
	IBM ThinkPad
	------------
	
	This laptop uses Western Digital controllers. Older versions of these laptops
	require the IBM VESA driver file to be loaded in Autoexec.bat (Ibmvesa.com) or
	in Config.sys (Vesa.exe) for 256-color and high-resolution modes to be supported
	by the Windows 95 Western Digital display driver. Newer versions of these
	laptops do not require the use of the IBM VESA driver.
	
	S3-Based Video Adapters
	-----------------------
	
	Windows 95 provides a hardware acceleration slider that can be used to correct
	graphics problems:
	
	- If you have problems with your mouse pointer, disable the hardware cursor by
	  setting the slider to the Most setting.
	
	- If you experience miscellaneous hangs with your S3 adapter, disable
	  memory-mapped I/O by setting the slider to the Basic setting.
	
	- If you have problems with a modem on COM 4, please see the following article
	  in the Microsoft Knowledge Base:
	
	  Q127138 S3 Video Driver Conflicts with COM4
	
	If you continue to have problems, try the None setting.
	
	For more information on how to use the slider to change the way Windows 95 uses
	the video card, please see the following article in the Microsoft Knowledge
	Base:
	
	  Q127139 Troubleshooting Video Problems in Windows 95
	
	Manually adding "HighColor=15" (no quotes) to the [Windows] section of the
	WIN.INI file corrects incorrect color at 16 bits per pixel using a 555 format.
	
	The products included here are manufactured by vendors independent of Microsoft;
	we make no warranty, implied or otherwise, regarding these products' performance
	or reliability.
	
	Additional query words: 3rdparty w95hwfaq
	
	======================================================================
	Keywords          : win95 
	Technology        : kbWin95search kbZNotKeyword3
	Version           : Win2000:95
	
	=============================================================================
	

{% endraw %}
