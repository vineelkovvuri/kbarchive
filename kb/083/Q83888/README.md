---
layout: page
title: "Q83888: XGA Driver Support in Windows 3.1"
permalink: /kb/083/Q83888/
---

## Q83888: XGA Driver Support in Windows 3.1

{% raw %}

	Article: Q83888
	Product(s): Microsoft Windows 95.x Retail Product
	Version(s): WINDOWS:3.0,3.0a,3.1
	Operating System(s): 
	Keyword(s): 
	Last Modified: 01-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows versions 3.0, 3.0a, 3.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Microsoft Windows operating system version 3.1 ships with the following drivers
	to support XGA:
	
	Driver     Display     Resolution              Memory on Adapter
	------     -------     ----------              -----------------
	
	VGA.DRV    XGA        (640 x 480, 16 colors)   512K
	XGA.DRV    XGA        (640 x 480, 256 colors)  512K
	XGA.DRV    XGA        (Large fonts)            512K or 1MB
	XGA.DRV    XGA        (Small fonts)            512K or 1MB
	
	- XGA (Small fonts) is for 1024 x 768, 256 colors with VGA fonts installed; it
	  allows more information to be seen on the screen at one time. XGA (Large
	  fonts) is for 1024 x 768, 256 colors with 8514 fonts installed; it makes text
	  on the screen larger and easier to read.
	
	- If you select XGA (Large fonts) or XGA (Small fonts) on a 512K XGA, Windows
	  will default to 1024 x 768, 16 colors if the attached monitor supports that
	  resolution (XGA on PS/2s can detect the monitor).
	
	NOTE Your monitor must be capable of these resolutions.
	
	MORE INFORMATION
	================
	
	The following are known issues with the XGA drivers that ship with Windows 3.1:
	
	1. By default, Windows Setup installs the XGA 640 x 480, 16-color driver. If you
	  have a monitor that can support the other resolutions listed above, you can
	  select another resolution.
	
	2. When you run the XGA 640 x 480, 16-color driver that uses the standard
	  VGA.DRV display driver, the colors displayed in MS-DOS applications running
	  in Windows may appear different from the same application running outside
	  Windows.
	
	3. If you are using a PS/2 Model 75 with a plasma screen, you must use the XGA
	  640 x 480, 16-color driver. With some PS/2 Model 75 plasma screens and with
	  XGA configured for 640 x 480 resolution and 16 colors, you must also include
	  the NOEMS or RAM option on the device=EMM386.EXE line in your CONFIG.SYS
	  file, as in the following example:
	
	        device=EMM386.EXE NOEMS X=C600-C7FF
	
	4. To use the IBM XGA successfully with EMM386.EXE, you must manually prevent
	  EMM386.EXE from using the memory address range used by the XGA display. To do
	  this, include the X= option on the device=EMM386.EXE line in your CONFIG.SYS
	  file, as in the following example:
	
	        device=EMM386.EXE  X=C600-C7FF
	
	  Replace "C600-C7FF" with the correct value for the address range used by your
	  XGA. To identify this range, run the System Configuration Program on the
	  System Reference Disk for your PS/2, and select "Display Memory Map."
	  C600-C7FF is a common range.
	
	5. Do not include the i=B000-BE00 option on the device=EMM386.EXE line in your
	  CONFIG.SYS file. This address range is used by the XGA when you run Windows
	  in 386 enhanced mode; therefore, it cannot be used as an upper memory area.
	  Windows will not recognize XGA configurations if EMM386.EXE is using this
	  address range.
	
	The IBM Extended Graphics Array (XGA) adapter is a memory-mapped graphics
	coprocessor for machines equipped with a Micro Channel Architecture (MCA) bus.
	The XGA adapter offers built-in VGA backward compatibility. The XGA adapter is
	shipped with 512K display memory (with an optional expansion to a total of 1
	MB). The IBM XGA is shipped as the standard display adapter for PS/2 models 90
	and 95.
	
	XGA memory-mapped registers occupy an 8K area in the Adapter Segment, between
	C000 and DFFF hexadecimal. By default it occupies the address space between C000
	and CFFF in the adapter segment. The default may be changed by using the
	reference disk that comes with the computer.
	
	The XGA adapter card is not 8514/A compatible. It cannot be used as a replacement
	for the 8514/A when you run CodeView for Windows (CVW) on a PS/2.
	
	XGA Drivers from IBM for Windows 3.0
	------------------------------------
	
	XGA adapters may include driver disks that include Windows 3.0 XGA display
	drivers. If your XGA card did not come with XGA video drivers, please contact
	your IBM dealer to obtain them.
	
	The IBM XGA support includes two drivers for Windows 3.0. These drivers support
	the following resolutions:
	
	                                      Memory
	  Driver     Resolution   Colors      Required
	  ------     ----------   ------      --------
	
	  XGALO.DRV  640 x 480    256 colors  512K
	  XGAHI.DRV  1024 x 768   16 colors   512K
	             1024 x 768   256 colors  1 MB
	
	Additional query words: 3.00 3.00a 3.10 3.11 code view 3rdparty
	
	======================================================================
	Keywords          :  
	Technology        : kbWin3xSearch kbZNotKeyword3 kbWin300 kbWin300a kbWin310
	Version           : WINDOWS:3.0,3.0a,3.1
	
	=============================================================================
	

{% endraw %}
