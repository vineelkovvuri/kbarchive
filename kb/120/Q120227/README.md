---
layout: page
title: "Q120227: Steps to Recover a Failed Mirrored System/Boot Partition"
permalink: /kb/120/Q120227/
---

## Q120227: Steps to Recover a Failed Mirrored System/Boot Partition

{% raw %}

	Article: Q120227
	Product(s): Microsoft Windows NT
	Version(s): winnt:3.1,3.5,3.51,4.0; :3.1
	Operating System(s): 
	Keyword(s): kbusage
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server versions 3.1, 3.5, 3.51, 4.0 
	- Microsoft Windows NT Workstation version 3.1 
	- Microsoft Windows NT Advanced Server, version 3.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Under some circumstances, the fault tolerance (FT) driver cannot initialize
	after a failure of a mirrored boot partition (containing Windows NT system
	files) and system partition (containing NTLDR and boot loader files). This
	article provides a step-by-step system recovery procedure for such a failure.
	
	MORE INFORMATION
	================
	
	There are two recovery options:
	
	Option 1
	--------
	
	1. If the hard disk drive with the primary system partition has failed and you
	  have a single controller mirror set established, set the physical SCSI ID on
	  the mirror drive to zero. If you have a duplex mirror set, swap the drive
	  from the primary controller to the secondary controller.
	
	2. Use a Windows NT Fault Tolerance (FT) boot floppy disk to point to and boot
	  the system/boot partition. Make sure the BOOT.INI file points to the
	  partition with the Windows NT system files.
	
	3. Open Disk Administrator, break the mirror set and mark the primary system
	  partition on Disk0 as Active so that the Windows NT FT disk is not necessary
	  for the next startup.
	
	4. If the failed drive has been replaced, establish the mirror set and allow
	  data regeneration during the next system boot.
	
	Option 2: No Hardware Changes
	-----------------------------
	
	1. Before breaking the mirror set in disk administrator, shut down the server
	  and use the Windows NT Fault Tolerance boot floppy disk to point to and boot
	  the remaining healthy partition (the mirror).
	
	2. Open Disk Administrator, select the mirror set partition and break the
	  mirror. The healthy partition retains the drive letter previously assigned to
	  the mirror set. The faulty partition, if it is still available, is assigned
	  the next available letter.
	
	3. Delete the faulty partition on Disk0 or replace the disk drive if necessary.
	  You cannot delete the active boot partition through Disk Administrator in
	  80x86-based computers; you have to use the Windows NT Setup Disk to delete
	  it.
	
	4. Establish the mirror between the healthy system/boot partition and the raw
	  disk space on Disk0. Exit Disk Administrator and save the disk configuration
	  changes.
	
	5. Use the Windows NT FT boot floppy to start regenerating the mirror set to
	  Disk0. Time required for this depends on factors such as disk size, access
	  time and controller type.
	
	6. Verify that the mirror set is healthy and has completed regenerating, then
	  select the set and break the mirror. You have to do this on 80x86- based
	  computers because the system partition needs to be marked as Active for
	  startup, and Disk Administrator allows you to mark only primary partitions on
	  Disk0 as Active.
	
	7. From Disk Administrator, modify the partition drive letters to have the
	  appropriate assignments (C drive on Disk0 and D drive on Disk1). Mark the
	  primary partition on Disk0 as Active.
	
	8. Reboot the system without the Windows NT FT boot floppy. Run Disk
	  Administrator and delete the partition on Disk1 and then re-establish the
	  mirror from Disk0 to Disk1.
	
	For additional information, please see the following articles in the Microsoft
	Knowledge Base:
	
	- Q108304: Recovering from Loss of FT Disk Configuration Information
	
	- Q113976: Using Emergency Repair Disk With Fault Tolerance Partitions
	
	- Q113977: Booting From Mirror After Primary Partition Is Lost
	
	- Q114779: Overview of Disk Mirroring (RAID Level 1) in Windows NT
	
	Additional query words: repair tshoot scsi dirty mirroring
	
	======================================================================
	Keywords          : kbusage 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNT351search kbWinNT350search kbWinNT400search kbWinNTW310 kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbWinNTS351 kbWinNTS350 kbWinNTS310 kbWinNTAdvSerSearch kbWinNTAdvServ310 kbWinNTS351search kbWinNTS350search kbWinNTS310search kbWinNT310Search kbWinNTW310Search
	Version           : winnt:3.1,3.5,3.51,4.0; :3.1
	
	=============================================================================
	

{% endraw %}
