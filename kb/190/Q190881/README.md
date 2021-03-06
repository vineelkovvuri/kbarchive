---
layout: page
title: "Q190881: Analyze6.exe Utility for Visual SourceSafe"
permalink: /kb/190/Q190881/
---

## Q190881: Analyze6.exe Utility for Visual SourceSafe

{% raw %}

	Article: Q190881
	Product(s): Microsoft SourceSafe
	Version(s): 4.0,4.0a,5.0
	Operating System(s): 
	Keyword(s): kbfile kbSSafe400 kbSSafe500 kbSSafe600 kbAnalyze kbFAQ kbDSupport kbSsafe600FAQ kbSSaf
	Last Modified: 22-JAN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual SourceSafe, 16-bit, for Windows, versions 4.0, 4.0a, 5.0 
	- Microsoft Visual SourceSafe, 32-bit, for Windows versions 4.0, 4.0a 
	- Microsoft Visual SourceSafe for Windows, version 5.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	
	Analyze6.exe is a file that contains the Analyze version 6.00.8169 utility.
	Analyze detects and validates all files in the database. It also enables you to
	fix any potential errors and remove files that are no longer active in the
	Visual SourceSafe database.
	
	The Analyze utility is a 32-bit utility that you can run under Windows NT,
	Windows 95, or Windows 98 in conjunction with the 32-bit Visual SourceSafe
	libraries. However, when you run it with the -f switch, it attempts to fix any
	data file in the SourceSafe Data directory, regardless of which platform the
	file originated from.
	
	MORE INFORMATION
	================
	
	NOTE: If you have upgraded to Microsoft Visual Studio Service Pack 5 (or later),
	you already have an improved version of the Analyze tool. For information on the
	latest service pack, see the following Microsoft Web site:
	
	  http://msdn.microsoft.com/ssafe/downloads/updates.asp
	
	The following files are available for download from the Microsoft Download
	Center:
	
	  Analyze6.exe
	
	For additional information about how to download Microsoft Support files, click
	the article number below to view the article in the Microsoft Knowledge Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	Microsoft used the most current virus detection software available on the date of
	posting to scan this file for viruses. Once posted, the file is housed on secure
	servers that prevent any unauthorized changes to the file.
	
	
	To install the Analyze utility, create a blank directory, copy Analyze6.exe to
	the directory, and run it. Analyze6.exe is a self-extracting file that contains
	Analyze.exe version 6.00.8169:
	
	  ssapi.dll
	  ssus.dll
	  mfc42.dll
	  msvcrt.dll
	  readme.txt
	
	NOTE: Do not install these files in the VSS\Win32 directory because it might
	disable the 32-bit version of Visual SourceSafe.
	
	When you run Analyze version 6.00.8169, all messages will scroll in the Analyze
	Results window. In the Analyze Results window, Analyze reports any errors it
	encounters and the fixes it performs. This information is also recorded in the
	Analyze.log file. Analyze contains a progress indicator in the status bar that
	lets you know the status of the clean up.
	
	If Analyze makes any changes to a file, it stores the file in a Backup directory,
	which, by default, is a subdirectory of the SourceSafe Data directory or of the
	directory that you run Analyze from. If the process does not finish, you can
	recover the original files (as they were before you started Analyze).
	
	By default, Analyze locks the data files while it analyzes them. Therefore, no
	one should be in Visual SourceSafe when you analyze the data files.
	
	Switches
	--------
	
	There are several switches in Analyze that allow you to perform functions on your
	database or individual files in the Data directory. These switches are:
	
	  Switch     Description
	  ----------------------------------------------------------------------
	
	  <none>     Analyze.exe, with no parameters, reports any errors that it
	             encounters in the database. This is similar to the behavior
	             of previous versions of Analyze. For example:
	
	             ANALYZE c:\ss\data
	             ANALYZE f:\ss\data\a\abaaaaaa
	
	             The Analyze Results window is displayed in Windows NT or
	             Windows 95. This window scrolls any errors it encounters.
	
	  -f         Fix. This enables Analyze to fix most of the errors it
	             encounters. To be successful, no users can be in Visual
	             SourceSafe. However, users can have files checked out. The
	             Visual SourceSafe administrator should wait until all users
	             are not running Visual SourceSafe before running Analyze with
	             the -f switch.
	
	             You need to have at least 16 MB of free hard drive space
	             available to run Analyze with the -f switch. In addition,
	             you should make enough hard drive space available for the
	             Backup directory. The size of the Backup directory is
	             determined by the number of corrupted files that Analyze
	             encounters.
	
	             Example:
	
	             ANALYZE ..\data -f
	
	
	  -i-        This switch enables you to keep the results window from
	             appearing. Example:
	
	             ANALYZE f:\ss\data -i-
	
	  -v         Verbose Logging. This allows Analyze to return all
	             information about the Analyze process to the lower pane of
	             the Analyze Results window. The upper pane of the Analyze
	             Results window is reserved for error conditions, and you
	             cannot turn it off. The -v switch has four option parameters
	             that indicate the amount of verbosity reported. By default,
	             it runs as -v1, which only shows errors. The -v4 option shows
	             all errors and informational messages. The other two options,
	             -v2 and -v3, fall in between. If no number is included, it
	             defaults to -v1.
	
	  -c        Compress. The -c switch allows Analyze to compress unused
	            comments that might exist in log files and free-up disk space.
	            However, this process is considerably slower and you should
	            not run it frequently. For example, you would have extraneous
	            information if you add a file and supply a comment at the time
	            of the Add and then you go back to the Properties on that file
	            later and change the comment. Now both comments are stored in
	            the data file. However, you cannot get access to the first
	            comment. If you run Analyze with -c and it discovers two
	            comments for a file, it rewrites the data file and leaves out
	            the older comment. While this switch can reduce the size of
	            the database in some cases, it usually does not make a
	            significant difference.
	
	  -d        Delete. -d enables Analyze to delete files that no longer have
	            valid references in Visual SourceSafe, such as files that were
	            branched into another project at one time, but no branched
	            versions of the file are now active in the database. Analyze
	            does an extensive comparison between projects and determines
	            which files can be successfully removed from the Data
	            directory. However, this can drastically slow down the Analyze
	            process so you might not want to perform this frequently.
	            Allow enough time for successful completion when you use the
	            -d switch. This switch reduces the size of the database only
	            if there are files that no longer have valid references in
	            Visual SourceSafe.
	
	  -b        Different backup directory. -b allows you to specify a
	            different backup directory. Make sure there is enough space in
	            this location to hold your entire Data directory contents,
	            should this be necessary.
	
	  -x        Do not lock. -x instructs Analyze not to lock the files as it
	            analyzes the database, so users can still use Visual
	            SourceSafe while Analyze is running. However, this switch
	            cannot be used with the -f, -d, and -c switches.
	
	
	Additional query words:
	
	======================================================================
	Keywords          : kbfile kbSSafe400 kbSSafe500 kbSSafe600 kbAnalyze kbFAQ kbDSupport kbSsafe600FAQ kbSSafeAnalyze 
	Technology        : kbSSafeSearch kbAudDeveloper kbSSafe400 kbSSafe400a kbSSafe500 kbSSafe16bitSearch kbSSafe32bitSearch
	Version           : :4.0,4.0a,5.0
	
	=============================================================================
	

{% endraw %}
