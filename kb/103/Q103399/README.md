---
layout: page
title: "Q103399: SAMPLE: NSetup.exe Reboots an MSSetup Script on User Request"
permalink: /kb/103/Q103399/
---

## Q103399: SAMPLE: NSetup.exe Reboots an MSSetup Script on User Request

{% raw %}

	Article: Q103399
	Product(s): Microsoft Windows Software Development Kit
	Version(s): WINDOWS:3.1
	Operating System(s): 
	Keyword(s): kbfile kbsample kb16bitonly
	Last Modified: 04-NOV-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows Software Development Kit (SDK) 3.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	NSetup.exe provides a mechanism for the user to communicate with the MSSetup
	dynamic-link libraries (DLLs) to cleanly reboot the computer without having a
	system file on the RestartList. The MSSetup Toolkit does not provide a way for
	the user to arbitrarily and cleanly reboot the computer without having the
	RestartListEmpty function return 0 (zero).
	
	MORE INFORMATION
	================
	
	The following file is available for download from the Microsoft Software
	Library:
	
	  NSetup.exe
	  (http://support.microsoft.com/download/support/mslfiles/NSetup.exe)
	
	For more information about downloading files from the Microsoft Software Library,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	
	The MSSetup Toolkit occupies a relatively small footprint in memory while
	providing much of the functionality needed to author a full-featured
	installation program. MSSetup accomplishes this low memory requirement by having
	a small fixed code stub program (SETUP.EXE) copy over the larger DLLs to a
	temporary directory on the user's hard disk. When the script exits, this small
	fixed code stub cleans up after the installation script by deleting the DLLs
	from the user's temporary directory.
	
	Another feature built into the MSSetup Toolkit is the ability to let the user
	install system level DLLs while they are loaded in memory at the time of
	installation. MSSetup accomplishes this by maintaining a list of files that need
	to be installed while Windows is rebooted. The MSSetup script author
	accomplishes this by calling the MSSetup functions RestartListEmpty and
	ExitExecRestart.
	
	There is no functionality built into the MSSetup Toolkit, however, to allow the
	user to arbitrarily reboot Windows. A cursory examination of this situation
	might yield a workaround involving the call to Windows-based application
	programming interface (API) ExitWindows or ExitWindowsExec via the MSSetup
	script. However, there is a problem with this approach. Upon rebooting the
	system, the user will find all the MSSetup DLLs still present in the temporary
	directory. Because Windows exits more or less immediately upon the call to
	ExitWindows or ExitWindowsExec, the Setup stub program (SETUP.EXE) never has a
	chance to perform its cleanup (see paragraph above). To expect the installation
	script to provide this type of functionality further complicates the situation.
	
	Another approach to the situation is to let MSSetup handle the cleanup as it
	would normally. NSETUP launches SETUP.EXE and waits for it to clean up and
	terminate. In this manner, NSETUP relies on SETUP.EXE's behavior to delete the
	files in the temporary directory. The sample also demonstrates a technique for
	communicating between the MSSetup script and the NSETUP program via the Windows
	function RegisterWindowMessage.
	
	In many ways, the NSETUP sample is similar to SETUP.EXE; it is a fixed code stub
	program, which WinExecs SETUP.EXE and then waits in the background for the
	program to finish. When SETUP.EXE finishes, NSETUP consults a reboot flag set
	via a message sent from the MSSetup script. If the user has chosen to reboot,
	NSETUP makes a call to ExitWindows.
	
	Additional query words: MSSetup tool kit
	
	======================================================================
	Keywords          : kbfile kbsample kb16bitonly 
	Technology        : kbAudDeveloper kbWin3xSearch kbSDKSearch kbWinSDKSearch kbWinSDK310
	Version           : WINDOWS:3.1
	
	=============================================================================
	

{% endraw %}
