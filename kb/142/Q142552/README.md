---
layout: page
title: "Q142552: FIX: OLE Error Playing .WAV Object"
permalink: /kb/142/Q142552/
---

## Q142552: FIX: OLE Error Playing .WAV Object

{% raw %}

	Article: Q142552
	Product(s): Microsoft FoxPro
	Version(s): 3.0 3.0b 5.0 5.0a
	Operating System(s): 
	Keyword(s): kbinterop kbvfp kbvfp300bBUG kbvfp500aBUG kbvfp500bug kbvfp600fixkbbuglist
	Last Modified: 23-MAR-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 3.0, 3.0b, 5.0, 5.0a 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	After clicking the icon to play a .wav file that is on a Visual FoxPro form, you
	sees a modal message box containing the text "OLE error code 0x80010105. The
	server threw an exception."
	
	WORKAROUND
	==========
	
	Ignore the message box. Click the OK button to remove the message from the form.
	Or play the .wav file programmatically. For more information on how to do this,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q102585 How to Play Waveform (.WAV) Files in FoxPro for Windows
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products listed at
	the beginning of this article. This has been corrected in Visual FoxPro 6.0.
	
	MORE INFORMATION
	================
	
	When you add an OLE container control to a form, add a .wav file to the OLE
	container, run the form, and click the .wav file icon, the sound plays, but a
	message box immediately appears stating that there has been an OLE error -- the
	server threw an exception.
	
	This happens regardless of whether Visual FoxPro is installed stand-alone or on a
	network, regardless of the operating system (Windows for Workgroups, Windows NT,
	or Windows 95), and regardless of which sound card and drivers you're using.
	
	Steps to Reproduce Problem
	--------------------------
	
	On a system that has a sound card and the appropriate driver software:
	
	1. Create a form by typing the following in the Command window:
	
	     Create form testx
	
	2. Add an OLE container control to the empty form (testx.scx).
	
	3. Click "Create from file" from the Insert Object dialog box, and then click
	  the Browse button. In the Browse dialog box, change the Directories to
	  C:\Windows. In the files list, select Chord.wav or any other .wav file. Click
	  OK to close the dialog boxes. A loudspeaker icon will appear on your form.
	
	4. Click the exclamation point (!) tool on the Visual FoxPro toolbar to run the
	  form.
	
	5. Double-click the loudspeaker icon to play the .wav file. The sound will play,
	  and immediately the message box will appear.
	
	Additional query words: media wave kbvfp600fix
	
	======================================================================
	Keywords          : kbinterop kbvfp kbvfp300bBUG kbvfp500aBUG kbvfp500bug kbvfp600fix kbbuglist
	Technology        : kbVFPsearch kbAudDeveloper kbVFP300 kbVFP300b kbVFP500 kbVFP500a
	Version           : 3.0 3.0b 5.0 5.0a
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
