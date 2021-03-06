---
layout: page
title: "Q105611: README.NOW: MS-DOS 6.2 Step-Up (BBS) README.NOW File"
permalink: /kb/105/Q105611/
---

## Q105611: README.NOW: MS-DOS 6.2 Step-Up (BBS) README.NOW File

{% raw %}

	Article: Q105611
	Product(s): Microsoft Disk Operating System
	Version(s): 6.2
	Operating System(s): 
	Keyword(s): 
	Last Modified: 26-FEB-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft MS-DOS operating system version 6.2 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article contains a complete listing of the MS-DOS 6.2 (downloadable
	version) README.NOW file.
	
	MORE INFORMATION
	================
	
	README.NOW
	
	Notes for MS-DOS 6.2 Step-Up Users
	----------------------------------
	
	The MS-DOS 6.2 Step-Up updates your system from MS-DOS 6 to MS-DOS 6.2.
	
	  IMPORTANT: To use the MS-DOS 6.2 Step-Up, you must be running the released
	  version of MS-DOS 6. If you are running an older version of MS-DOS, a beta
	  version of MS-DOS 6, or any version of MS-DOS that was modified by a hardware
	  vendor, you cannot use the MS-DOS 6.2 Step-Up. To install MS-DOS 6.2 on such
	  a system, obtain the full MS-DOS 6.2 Upgrade product.
	
	This file explains how to upgrade to MS-DOS 6.2; it contains information specific
	to the Step-Up installation process. If you don't find the information you need
	in this file, see the README.TXT file, which is located in the directory that
	contains your MS-DOS files or on Setup Disk 1 of your MS-DOS 6.0 disk set.
	
	This file contains the following topics:
	
	1. What MS-DOS 6.2 Step-Up includes
	
	2. Upgrading to MS-DOS 6.2
	
	  2.1 Installing MS-DOS 6.2
	  2.2 If your MS-DOS 6 files are not located on drive C
	  2.3 If Setup cannot update a file
	  2.4 If Setup cannot find the correct IO.SYS file
	  2.5 Installing MS-DOS 6.2 without using SETUP.BAT
	
	3. Using the MakeSys Program
	
	  3.1 If MakeSys could not create your IO.SYS, MSDOS.SYS or DBLSPACE.BIN file
	  3.2 Using MakeSys if you are running Dutch or Italian MS-DOS 6
	
	4. Updating Microsoft Backup, Undelete and Antivirus
	
	  4.1 If you have not yet installed MS-DOS 6.2
	  4.2 If you have already installed MS-DOS 6.2
	
	5. Keeping a Copy of the MS-DOS 6.2 Step-Up
	
	6. Reading the README.TXT file on Setup Disk 1
	
	1. What MS-DOS 6.2 Step-Up Includes
	-----------------------------------
	
	The MS-DOS 6.2 Step-Up includes all changes that were made to the MS-DOS files
	since MS-DOS 6. Most of the files included with the MS-DOS 6.2 Step-Up simply
	specify changes for MS-DOS 6.2 and are not complete programs. MS-DOS 6.2 Setup
	uses these files to update the files on your hard disk to MS-DOS 6.2. To do
	this, Setup must be able to find and update each of your MS-DOS 6 files.
	
	2.  Upgrading to MS-DOS 6.2
	---------------------------
	
	This section explains how to update your system to MS-DOS 6.2.
	
	  Note: If you did not install the MS-DOS 6 optional programs (Backup,
	  AntiVirus and Undelete), then MS-DOS 6.2 Setup cannot update those programs
	  to version 6.2. If you want the MS-DOS 6.2 versions of these programs, carry
	  out the procedure in section 4 of this file before installing MS-DOS 6.2.
	
	2.1  Installing MS-DOS 6.2:
	
	To update your system to MS-DOS 6.2, your computer must already be running MS-DOS
	6. To install MS-DOS 6.2, follow these steps:
	
	1. If Windows is running, quit Windows.
	
	2. At the command prompt, type VER to ensure that you are running the release
	  version of MS-DOS 6.0.
	
	3. Change to the directory that contains the SETUP.BAT file and the 1MSDOS62.EXE
	  and 2MSDOS62.EXE files, and then type SETUP at the command prompt.
	
	  The SETUP.BAT batch program creates the C:\STEPUP directory and extracts the
	  MS-DOS 6.2 Step-Up files from the archive files (1MSDOS62.EXE and
	  2MSDOS62.EXE). SETUP.BAT then runs the MAKESYS utility to create the MS-DOS
	  6.2 system files. Finally, it runs MS-DOS 6.2 Setup.
	
	  NOTE: If your MS-DOS 6 files are located on a drive other than drive C, quit
	  MS-DOS Setup by pressing F3, and then carry out the procedure in the
	  following section.
	
	When Setup is complete, do not delete the files in your Step-Up directory. Also,
	do not discard your MS-DOS 6 disks. For more information, see Section 5 of this
	file.
	
	If the MAKESYS or Setup programs do not complete properly, see section 2.5 of
	this file.
	
	2.2  If your MS-DOS 6 files are not located on drive C:
	
	The MS-DOS 6.2 Step-Up is designed to update MS-DOS 6 files that are located on
	drive C. If your MS-DOS 6 files are located on a drive other than drive C,
	follow these steps:
	
	1. First, carry out the procedure in section 2.1. When MS-DOS 6.2 Setup starts,
	  quit Setup by pressing F3.
	
	2. Create a new directory on drive C (for example, C:\DOS).
	
	3. Copy your MS-DOS 6 files to that directory. For example, if your MS-DOS 6
	  files are located in the D:\DOS directory and you want to copy them to the
	  C:\DOS directory, you would type:
	
	  " COPY D:\DOS\*.* C:\DOS" (without the quotation marks)
	
	4. Change to the C:\STEPUP directory, and then type SETUP. When Setup displays
	  the directory that contains your current MS-DOS files, type the pathname of
	  the directory you just created on drive C (for example, C:\DOS).
	
	5. When Setup is complete, MS-DOS 6.2 will be installed on drive C. Setup
	  updates the pathnames in your CONFIG.SYS and AUTOEXEC.BAT files so that they
	  refer to the directory on drive C that contains your MS-DOS 6.2 files.
	
	  If you want to move MS-DOS 6.2 back to the other drive, copy all the MS-DOS
	  6.2 files to a directory on the other drive. You will also need to correct
	  the pathnames in your CONFIG.SYS and AUTOEXEC.BAT files to refer to the
	  correct drive and directory.
	
	2.3  If Setup cannot update a file:
	
	If Setup cannot update one of your MS-DOS files, it displays a message with the
	title "Cannot Update File." If you continued Setup, your MS-DOS 6.2 installation
	is incomplete because the specified file was not updated to version 6.2. If the
	file is one you know you don't need, don't worry about it. However, if you are
	not sure, update the file using the following procedure.
	
	1. Insert MS-DOS 6 Setup Disk 1 in drive A or drive B, and then use MS-DOS
	  Editor (EDIT) to view the contents of the PACKING.LST file. This file tells
	  you where each file is located on your MS-DOS 6 disks. Determine which MS-DOS
	  6 disk contains the file you need.
	
	2. Insert the appropriate MS-DOS 6 disk in drive A or drive B, and then use the
	  EXPAND command to expand the file. For example, to expand the file
	  DBLSPACE.HL_ from the disk in drive A to the directory C:\DOS, you would type
	  the following command:
	
	  " EXPAND A:\DBLSPACE.HL_ C:\DOS\DBLSPACE.HLP" (without the quotation marks)
	
	  For more information, see the comments at the beginning of the PACKING.LST
	  file, or see the MS-DOS 6 User's Guide.
	
	3. Run MS-DOS 6.2 Setup again. This time, Setup should be able to update the
	  file.
	
	If you follow this procedure and Setup still cannot update the file, there may be
	a problem with your MS-DOS 6.2 Step-Up files. You may be able to correct the
	problem by running ScanDisk on the drive that contains your Step-Up files.
	
	2.4  If Setup cannot find the correct IO.SYS file:
	
	If Setup cannot find the correct IO.SYS file, one of the following may be the
	cause of the problem:
	
	- You are not running a released version of MS-DOS 6 or 6.2.
	
	  To use the MS-DOS 6.2 Step-Up, you must be running the released version of
	  MS-DOS 6 or 6.2. The Step-Up will not work on other versions of MS-DOS, on
	  other manufacturers' operating systems, or on beta versions of MS-DOS.
	
	- Your IO.SYS file has been damaged or modified.
	
	  Setup cannot update an IO.SYS file that has been corrupted (for example, by a
	  virus or a hard disk error) or an IO.SYS file that has been modified by
	  another program (such as an MS-DOS extender). If you suspect this is the
	  problem, use the SYS command to copy the system files from Setup Disk 1 of
	  your MS-DOS 6 disks.
	
	- You are running a version of MS-DOS in a language that is different from this
	  version of the MS-DOS 6.2 Step-Up. If this is the problem, obtain the MS-DOS
	  6.2 Step-Up for the same language as your current version of MS-DOS.
	
	2.5  Installing MS-DOS 6.2 without using SETUP.BAT:
	
	Normally, you use the SETUP.BAT batch program to prepare your system to run
	MS-DOS 6.2 Setup; SETUP.BAT does everything for you, including starting Setup.
	However, if the MAKESYS or Setup programs do not complete properly, you may need
	to perform some or all of the installation process without using SETUP.BAT. This
	section explains how to install MS-DOS 6.2 without running SETUP.BAT:
	
	To install MS-DOS 6.2 without using SETUP.BAT, follow these steps:
	
	1. If Windows is running, quit Windows.
	
	2. At the command prompt, type "VER" (without the quotation marks) to ensure
	  that you are running the release version of MS-DOS 6.0.
	
	3. Create a C:\STEPUP directory by typing the following at the command prompt:
	
	  " MD C:\STEPUP" (without the quotation marks)
	
	4. Copy the 1MSDOS62.EXE and 2MSDOS62.EXE files into the C:\STEPUP directory.
	
	  IMPORTANT: Do not place these files in the directory that currently contains
	  your MS-DOS 6 files. If you do, the Step-Up process will not work properly.
	
	5. Change to the C:\STEPUP directory, and then run the 1MSDOS62.EXE and
	  2MSDOS62.EXE programs by typing the following:
	
	  " 1MSDOS62
	  2MSDOS62" (without the quotation marks)
	
	  When these programs finish running, the C:\STEPUP directory will contain the
	  files you need to update your system to MS-DOS version 6.2.
	
	6. Run the MAKESYS.EXE program by typing "MAKESYS" (without the quotation marks)
	  at the command prompt.
	
	  MAKESYS creates the MS-DOS 6.2 system files in the C:\STEPUP directory. These
	  files are required by MS-DOS 6.2 Setup.
	
	7. If your MS-DOS 6 files are located on drive C, run MS-DOS 6.2 Setup by typing
	  SETUP, and then follow the instructions on the screen. (If your MS-DOS 6
	  files are located on a drive other than drive C, carry out the procedure in
	  the following section.)
	
	  IMPORTANT: When Setup is complete, do not delete the files in your Step-Up
	  directory. Also, do not discard your MS-DOS 6 disks. For more information,
	  see "Keeping a Copy of the MS-DOS 6.2 Step-Up" later in this file.
	
	3. Using the MakeSys Program
	----------------------------
	
	The MakeSys program creates a set of MS-DOS 6.2 system files in the current
	directory. These files are required by MS-DOS 6.2 Setup.
	
	This section provides some procedures for troubleshooting MakeSys. For
	information about running MakeSys, see the procedure in section 2.5.
	
	3.1  If MakeSys could not create your IO.SYS, MSDOS.SYS or DBLSPACE.BIN file:
	
	If MakeSys displays the message "Could not create the new IO.SYS file," "Could
	not create the new MSDOS.SYS file," or "Could not create the new DBLSPACE.BIN
	file," then one of the following may be the cause of the problem:
	
	- MakeSys was unable to find a valid MS-DOS 6 version of that file; either you
	  are not running the official released version of MS-DOS 6, or the file is not
	  in the expected location.
	
	  The procedure you use depends on whether you are using DoubleSpace. If you do
	  not use DoubleSpace, follow these steps:
	
	  1. Run MakeSys again by typing MAKESYS at the command prompt.
	
	     MakeSys starts, and displays the prompt "MakeSys has determined that your
	     startup hard disk is drive C. Is this correct (Y/N)?"
	
	  2. Type "N" (without the quotation marks).
	
	     MakeSys then displays the prompt "Enter the drive letter of your startup
	     hard disk or press CTRL+C to exit."
	
	  3. Insert MS-DOS 6 Setup Disk 1 in drive A or drive B, and then type the
	     appropriate drive letter and press ENTER.
	
	     MakeSys uses the system files on MS-DOS 6 Setup Disk 1 to create MS-DOS 6.2
	     system files in the C:\STEPUP directory.
	
	  4. Run MS-DOS 6.2 Setup by typing "SETUP" (without the quotation marks).
	
	If you use DoubleSpace, carry out these steps:
	
	  1. If you use Windows NT as well as DoubleSpace, make sure you have your
	     Windows NT Setup disks and the Windows NT Emergency Repair Disk that you
	     made for this computer.
	
	  2. Use the SYS command to copy the MS-DOS 6 system files from MS-DOS 6 Setup
	     Disk 1 to your startup drive. For example, to copy the system files from
	     Setup Disk 1 in drive A, type the following:
	
	  " SYS A: C:" (without the quotation marks)
	
	  3. Run MakeSys again.
	
	  4. If you use Windows NT, insert your Windows NT Setup Disk and restart your
	     computer. Then, use the Repair option to repair the Windows NT boot files.
	     After the repair is complete, return to the MS-DOS command prompt.
	
	  5. Change to the C:\STEPUP directory, and then run MS-DOS 6.2 Setup by typing
	     "SETUP" (without the quotation marks).
	
	3.2  Using MakeSys if you are running Dutch or Italian MS-DOS 6:
	
	If you are running the Dutch or Italian version of MS-DOS 6 and MakeSys displays
	the message "Could not create the new MSDOS.SYS file," follow these steps:
	
	  1. Change to the directory that contains your MS-DOS 6.2 Step-Up files.
	
	  2. Type the following commands:
	
	  " REN MSDOS.SY# MSDOS.XX#
	  REN MSDOS2.SY# MSDOS.SY#" (without the quotation marks)
	
	  3. Run MakeSys again.
	
	4. Updating Microsoft Backup, Undelete and Antivirus
	----------------------------------------------------
	
	MS-DOS 6.2 Setup automatically updates the Backup, Undelete and Antivirus
	programs only if the MS-DOS 6 versions of these programs are already on your
	computer when you run MS-DOS 6.2 Setup. If you want the MS-DOS 6.2 versions of
	these programs, but the MS-DOS 6 versions are not currently installed on your
	system, carry the procedure in section 4.1 or 4.2 (depending on whether you have
	installed MS-DOS 6.2 yet).
	
	4.1 If you have not yet installed MS-DOS 6.2:
	
	The easiest way to install the MS-DOS 6.2 versions of Backup, Undelete and
	Antivirus is to install the MS-DOS 6 versions of those programs before you
	install MS-DOS 6.2. Follow these steps:
	
	  1. Insert MS-DOS 6 Setup Disk 1 in drive A or drive B.
	
	  2. Type "A:SETUP /E" (without the quotation marks) or "B:SETUP /E" (without
	     the quotation marks) at the command prompt, and then follow the
	     instructions on your screen.
	
	  3. Install MS-DOS 6.2 as described in Section 2 of this file.
	
	4.2 If you have already installed MS-DOS 6.2:
	
	If Backup, Undelete, or Antivirus were not on your system when you installed
	MS-DOS 6.2, but you later decided that you want the MS-DOS 6.2 versions of those
	programs, carry out one of the following procedures (depending on whether your
	MS-DOS 6 disks fit in drive A). Procedure 1: Updating the optional programs if
	your MS-DOS 6 disks fit in drive A
	
	If your MS-DOS 6 disks fit in drive A, follow these steps:
	
	  1. Insert MS-DOS 6 Setup Disk 1 in drive A, and restart your computer. (If
	     your MS-DOS 6 disks do not fit in drive A, carry out Procedure 2 instead.)
	
	  2. The Welcome screen for MS-DOS 6 Setup appears. Press the F3 key twice to
	     exit.
	
	  3. Use the PATH command to ensure that your current search path includes the
	     directory that contains your MS-DOS 6.2 files. For example, if your MS-DOS
	     6.2 files are in C:\DOS, you would type
	
	  " PATH C:\DOS" (without the quotation marks)
	
	     Note: Be sure to specify the drive letter in uppercase.
	
	  4. Change to the drive that contains MS-DOS 6 Setup Disk 1, and then type the
	     following:
	
	  " SETUP /E" (without the quotation marks)
	
	     Select the optional programs you want. When MS-DOS Setup is complete,
	     remove MS-DOS 6 Setup Disk 1 and restart your computer.
	
	  5. Change to the C:\STEPUP directory, and then run MS-DOS 6.2 Setup by typing
	     "SETUP" (without the quotation marks).
	
	Procedure 2: Updating the optional programs if your MS-DOS 6 disks don't fit in
	drive A
	
	If your MS-DOS 6 disks do not fit in drive A, follow these steps:
	
	  1. Create an MS-DOS 6 startup floppy disk by inserting your MS-DOS 6 Setup
	     Disk 1 in drive B and typing the following:
	
	  " B:SETUP /F" (without the quotation marks)
	
	  2. When Setup displays the settings it will use, the "Install on Drive:"
	     setting will specify drive B. Change this setting to drive A.
	
	     Setup then creates a startup floppy disk. To complete Setup, follow the
	     instructions on your screen.
	
	  3. Restart your computer from the MS-DOS 6 startup floppy disk you just
	     created (leave the disk in drive A, and press CTRL+ALT+DEL).
	
	  4. Use the PATH command to ensure that your current search path includes the
	     directory that contains your MS-DOS 6.2 files. For example, if your MS-DOS
	     6.2 files are in C:\DOS, you would type
	
	  " PATH C:\DOS" (without the quotation marks)
	
	     Note: Be sure to specify the drive letter in uppercase.
	
	  5. Change to the drive that contains MS-DOS 6 Setup Disk 1, and then type the
	     following to install the optional MS-DOS 6 programs:
	
	  " SETUP /E" (without the quotation marks)
	
	     Select the optional programs you want. When MS-DOS Setup is complete,
	     remove MS-DOS 6 Setup Disk 1 and restart your computer.
	
	  6. Change to the C:\STEPUP directory, and then run MS-DOS 6.2 Setup by typing
	     SETUP.
	
	5. Keeping a Copy of the MS-DOS 6.2 Step-Up
	-------------------------------------------
	
	After you have finished installing MS-DOS 6.2, do not delete the files in your
	Step-Up directory. If you ever need to reinstall MS-DOS 6.2, you will need the
	Step-Up files as well as your MS-DOS 6 disks.
	
	To ensure that you can reinstall MS-DOS 6.2, follow these steps:
	
	  1. Make sure your MS-DOS 6 disks are in a safe place.
	
	  2. Copy the following files from your MS-DOS 6.2 Step-Up directory to floppy
	     disks, and keep the floppy disk in a safe place. (You will need two 1.2MB
	     or 1.44 MB floppy disks.)
	
	  SETUP.BAT
	  README.NOW
	  1MSDOS62.EXE
	  2MSDOS62.EXE
	
	  3. Make an MS-DOS 6.2 startup floppy disk by using the SYS command. For
	     example, if your computer's startup floppy disk drive is drive A, you
	     would insert a floppy disk in drive A and type the following:
	
	  " SYS A:" (without the quotation marks)
	
	  4. After completing steps 1 through 3, you can safely delete the files in
	     your Step-Up directory.
	
	6. Reading the README.TXT file on Setup Disk 1
	----------------------------------------------
	
	After you install MS-DOS 6.2, a copy of the README.TXT file will be located in
	the directory that contains your MS-DOS files. To read this file, change to that
	directory, and then type the following at the command prompt:
	
	  " EDIT README.TXT" (without the quotation marks)
	
	If you need to, you can read the copy of README.TXT located on Setup Disk 1. To
	do this:
	
	  1. Insert Setup Disk 1 in a floppy disk drive, and then make that drive your
	     current drive. For example, if the disk is in drive A, type "A:" (without
	     the quotation marks).
	
	  2. At the command prompt, type the following command:
	
	  " EXPAND README.TX_ C:\README.TXT" (without the quotation marks)
	
	  3. You should then be able to use the EDIT command to view the C:\README.TXT
	     file.
	
	Additional query words: msbackup 6.20 bbsstepup stepup tools extra
	
	======================================================================
	Keywords          :  
	Technology        : kbMSDOSSearch kbMSDOS620
	Version           : :6.2
	
	=============================================================================
	

{% endraw %}
