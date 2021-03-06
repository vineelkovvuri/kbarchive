---
layout: page
title: "Q156566: XCLN: Comparing MMF and PST File Sizes"
permalink: /kb/156/Q156566/
---

## Q156566: XCLN: Comparing MMF and PST File Sizes

{% raw %}

	Article: Q156566
	Product(s): Microsoft Exchange
	Version(s): WINDOWS:4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 15-JAN-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Windows 3.x client, version 4.0 
	- Microsoft Exchange Windows 95/98 client, version 4.0 
	- Microsoft Exchange Windows NT client, version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	If you used Microsoft Mail before migrating to Microsoft Exchange, you might
	have message files (MMF files) that you want to move to Microsoft Exchange. To
	do so, you must convert the information from its original format to a PST file.
	You can then add this file to your active profile. To see the steps to import an
	MMF file, please see the Microsoft Exchange Client Help topic on Importing MMF
	files. This article discusses the file size differences between MMF and PST
	files.
	
	MORE INFORMATION
	================
	
	MMF Smaller than PST:
	
	When an MMF file is converted to a PST file, the size difference will be
	noticeable. The PST file will usually be larger than the original MMF file. This
	is due to the way that PST files store Compressed RTF and Message Body for each
	message. MMF files only store Message Body format and not the Compressed RTF
	format.
	
	MMF imported into Microsoft Exchange Mailbox Folder:
	
	Migrating the same MMF file to a Microsoft Exchange Server Mailbox folder will
	cause less data to be stored on the Microsoft Exchange Server. This is because
	it only stores the RTF part of the message and it is compressed. Compressed RTF
	is usually smaller than the original plain-text body.
	
	PST Smaller than MMF:
	
	A non-compacted MMF file that is converted to a PST file can actually yield a PST
	file that is smaller than the source MMF file. In addition, if the source MMF
	file has corrupt messages in it, those messages will be deleted by the migration
	utility, resulting in a smaller PST file.
	
	TIP: To reduce the size of your MMF file, discard messages that you no longer
	need and compact the file before importing it.
	
	PST encryption is a direct byte substitution for the original data, so a PST file
	with encryption will be the same size as an otherwise identical PST file without
	encryption.
	
	Additional query words: 4.00
	
	======================================================================
	Keywords          :  
	Technology        : kbExchangeSearch kbExchange400 kbExchangeClientSearch kbZNotKeyword kbZNotKeyword2 kbZNotKeyword3 kbExchange400NT kbExchange400Win95
	Version           : WINDOWS:4.0
	
	=============================================================================
	

{% endraw %}
