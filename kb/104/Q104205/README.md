---
layout: page
title: "Q104205: How to Remove an Extended NTFS Partition"
permalink: /kb/104/Q104205/
---

## Q104205: How to Remove an Extended NTFS Partition

{% raw %}

	Article: Q104205
	Product(s): Microsoft Windows NT
	Version(s): 3.1,3.5,3.51,4.0
	Operating System(s): 
	Keyword(s): kbother
	Last Modified: 28-FEB-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server versions 3.1, 3.5, 3.51, 4.0 
	- Microsoft Windows NT Workstation versions 3.1, 3.5, 3.51, 4.0 
	- Microsoft Windows NT Advanced Server, version 3.1 
	-------------------------------------------------------------------------------
	
	If you have a logical drive in an extended partition that has been
	formatted with NTFS, it can be removed using Disk Administrator unless
	Windows NT has been installed on the partition. If Windows NT resides
	on the same partition, you need to use either of the following two
	procedures.
	
	NOTE: Removing a partition requires that you back up any important
	information beforehand, as each procedure below will destroy all the
	data on your extended NTFS partition. If you plan to remove the entire
	extended partition, all logical drives within it will be destroyed as
	well. In this case, make sure you back up data on all logical drives.
	
	WINDOWS NT 3.5x and 4.0
	-----------------------
	
	NOTE: To return to MS-DOS as your primary operating system, drive C must be
	formatted as FAT. If you do not want to return to MS-DOS, skip steps 3 and
	If you only want to change the file system back to FAT for the logical
	drive that Windows NT is installed on, skip step 2 for any NTFS drive you
	wish to keep, and steps 3 and 4.
	
	1. Backup any data you want to keep on any NTFS logical drives or partitions.
	
	2. Use Disk Administrator to remove all NTFS drives except the drive Windows NT
	  is installed on. If drive C is NTFS, you must recreate the partition as FAT.
	
	3. Boot with an MS-DOS floppy disk which has the SYS command on it.
	
	4. From drive A, type:
	
	  sys c:
	
	5. Boot with the Windows NT Setup Disk and run custom setup. For speed purposes
	  it is best to skip the mass storage detection and manually specify any
	  supported SCSI compliant adapters you have. If you have a CD-ROM drive, you
	  will have a choice of installing from either the CD or 3.5" disks in drive A.
	
	6. If Setup finds a copy of Windows NT to upgrade, press N to have Windows NT
	  not upgrade the existing copy.
	
	7. Press ENTER after confirming the hardware list matches the hardware you are
	  using.
	
	8. If Setup finds a copy of Windows, press N to not have Windows NT installed
	  into the Windows directory.
	
	9. You will be at the partitioning screen next. On this screen you will have the
	  choice to delete the NTFS partition. Select the NTFS partition to be deleted.
	  To select the partition use the up and down arrow keys.
	
	10. Press D to delete the partition.
	
	11. Press L to confirm the deletion.
	
	12. You will be back in the partition screen. Select the unpartitioned space by
	  using the up and down arrow keys. Press ENTER to have Windows NT installed
	  on that partition.
	
	13. Choose to have the partition formatted as FAT and press ENTER.
	
	14. When the format is complete, Setup will ask for a path for Windows NT to be
	  installed into. If you want to keep Windows NT, either change the path or
	  accept the default and finish setup. If you want to go back to MS-DOS, press
	  the F3 function key twice to exit Setup. Remove any floppy disks in drive A
	  and press ENTER to reboot the system.
	
	WINDOWS NT AND WINDOWS NT ADVANCED SERVER VERSION 3.1
	-----------------------------------------------------
	
	Using Setup Disk Created by WINNT.EXE:
	
	NOTE: This procedure requires that you have a FAT partition somewhere
	on your first hard disk drive. If all your partitions are NTFS or
	HPFS, this procedure will not work.
	
	1. From Boot Loader, choose MS-DOS for your operating system, or restart your
	  computer with a bootable MS-DOS floppy disk inserted.
	
	2. Type the following command line:
	
	  md c:\$win_nt$.~ls
	
	  This directory's existence is checked for by the setup disk WINNT.EXE creates.
	
	3. Insert the disk created by WINNT.EXE during setup and restart your computer.
	
	4. Do as directed by Windows NT Setup, choosing Custom when prompted for the
	  type of setup.
	
	5. At one point, Setup will display an error message similar to the following:
	
	  Unable to load file system support. The distribution disk may be damaged.
	
	  Ignore this message and press ENTER. Choose any path when prompted.
	
	6. When you have the option to choose which partition to install to, note that
	  the NTFS partition is labeled "Unknown or unformatted." Choose this partition
	  and press P to create or delete a partition.
	
	7. On the next Setup screen press ENTER to remove the "non-partition." Press
	  ENTER again to return to the partition choices.
	
	8. Press F3 twice to quit Setup and restart your computer.
	
	Using Norton Disk Edit:
	
	1. Start Norton Disk Edit.
	
	2. From the Object menu, choose Drive.
	
	3. Choose Physical Disks.
	
	4. Choose Drive and choose OK.
	
	5. Select the hard disk that contains the NTFS partition.
	
	6. From the View menu, choose Partition Table.
	
	7. Select the partition marked "EXTEND" and press ENTER to look at the extended
	  partition.
	
	8. Look for an entry in the extended partition table that reads "HPFS." If you
	  cannot find the "HPFS" partition, look for another "EXTEND" partition,
	  highlight it and press ENTER again. Do this until you have found the
	  partition marked "HPFS."
	
	9. Highlight the partition marked "HPFS" and press the SPACEBAR until it reads
	  "Unused."
	
	10. Exit Norton's Disk Edit, making sure to save the changes.
	
	11. Use the MS-DOS FDISK command or Disk Administrator to re-create the deleted
	  partition.
	
	Additional query words: prodnt 3.10
	
	======================================================================
	Keywords          : kbother 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNTW400 kbWinNTW400search kbWinNT351search kbWinNT350search kbWinNT400search kbWinNTW350 kbWinNTW350search kbWinNTW351search kbWinNTW351 kbWinNTW310 kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbWinNTS351 kbWinNTS350 kbWinNTS310 kbWinNTAdvSerSearch kbWinNTAdvServ310 kbWinNTS351search kbWinNTS350search kbWinNTS310search kbWinNT310Search kbWinNTW310Search
	Version           : :3.1,3.5,3.51,4.0
	
	=============================================================================
	

{% endraw %}
