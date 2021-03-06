---
layout: page
title: "Q302888: HOWTO: Schedule Metabase Backups Using WSH"
permalink: /kb/302/Q302888/
---

## Q302888: HOWTO: Schedule Metabase Backups Using WSH

{% raw %}

	Article: Q302888
	Product(s): Internet Information Server
	Version(s): 5.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 13-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Internet Information Services version 5.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article provides a sample script that can be used to back up the Internet
	Information Services (IIS) metabase as a scheduled task by using Windows Script
	Host (WSH).
	
	MORE INFORMATION
	================
	
	WARNING: ANY USE BY YOU OF THE CODE PROVIDED IN THIS ARTICLE IS AT YOUR OWN
	RISK. Microsoft provides this code "as is" without warranty of any kind, either
	express or implied, including but not limited to the implied warranties of
	merchantability and/or fitness for a particular purpose.
	
	IIS supports programmatic administration of the metabase using the Active
	Directory Servies Interface (ADSI). The sample script that is listed below
	creates a backup of the metabase that will be stored in the following path:
	
	  %SystemRoot%\System32\InetSrv\MetaBack
	
	NOTE: This folder is a fixed location and cannot be changed.
	
	To create the sample WSH script and a scheduled task to run the script, follow
	these steps:
	
	1. Save the following code in your C:\Inetpub\Adminscripts folder as
	  Mbackup.vbs:
	
	  '****************************************
	  ' Description:
	  '   Metabase Backup Utility   
	  ' Syntax:
	  '   CSCRIPT MBACKUP.VBS
	  '****************************************
	
	  Option Explicit
	  On Error Resume Next
	
	  ' Declare variables.
	  Dim strBackupName, lngBackupVersion, lngBackupFlags
	  Dim objComputer
	  Dim strDay, strMonth, strYear
	
	  ' Get the current DD/MM/YY as strings.
	  strDay   = Right("00" & Cstr(Day(Date())),2)
	  strMonth = Right("00" & Cstr(Month(Date())),2)
	  strYear  = Cstr(Year(Date()))
	
	  ' Create a file name from the current date.
	  strBackupName = strYear & "-" & strMonth & "-" & strDay
	
	  ' Use the next available version number.
	  lngBackupVersion = &HFFFFFFFF
	  lngBackupFlags = 0
	   
	  ' Output the backup message.
	  Wscript.Echo "Backing up metabase to file: """ & strBackupName & """"
	
	  ' Get the ADSI object.
	  Set objComputer = GetObject("IIS://LOCALHOST")
	
	  ' Call the backup method.
	  objComputer.Backup strBackupName, lngBackupVersion, lngBackupFlags
	
	  ' Check for errors.  
	  If Err.Number <> 0 Then
	    Wscript.Echo "Error: "  & Err.Description & " (0x" & Right(String(8,"0") & Hex(Err.Number),8) & ")"
	  Else
	    Wscript.Echo "Success."
	  End If
	
	NOTE: The following code can be appended to the previous sample to delete old
	backups. To customize this, change the value of the lngBackupToDelete variable
	in the script.
	
	  '****************************************
	  ' The remaining code is optional and deletes a specific older backup.
	  '****************************************
	
	  ' The value of lngBackupToDelete determines which specific date to delete
	  ' in this case. 28 days is four weeks ago if you are running a weekly backup.
	  Const lngBackupToDelete = 28 
	
	  ' Declare variables.
	  Dim strOldDay, strOldMonth, strOldYear, strOldBackupName
	
	  ' Get the old DD/MM/YY as strings.
	  strOldDay   = Right("00" & Cstr(Day(Date()-lngBackupToDelete)),2)
	  strOldMonth = Right("00" & Cstr(Month(Date()-lngBackupToDelete)),2)
	  strOldYear  = Cstr(Year(Date()-lngBackupToDelete))
	
	  ' Create the file name from the old date.
	  strOldBackupName = strOldYear & "-" & strOldMonth & "-" & strOldDay
	
	  ' Output the deletion message.
	  Wscript.Echo "Deleting metabase backup file: """ & strOldBackupName & """"
	
	  ' Call the deletion method.
	  objComputer.DeleteBackup strOldBackupName, 0
	
	  ' Check for errors.  
	  If Err.Number <> 0 Then
	    If Err.Number = &H80070002 Then
	      Wscript.Echo "File not found."
	    Else
	      Wscript.Echo "Error: "  & Err.Description & " (0x" & Right(String(8,"0") & Hex(Err.Number),8) & ")"
	    End If
	  Else
	    Wscript.Echo "Success."
	  End If
	
	2. Create a task to schedule the backup script. At a command prompt, type a
	  command similar to the following:
	
	   - For a task that runs every Monday at 6:00am:
	
	  AT 6:00am /every:M cscript.exe c:\inetpub\adminscripts\mbackup.vbs
	
	   - For a task that runs once at 9:00pm:
	
	  AT 9:00pm cscript.exe c:\inetpub\adminscripts\mbackup.vbs
	
	   - For a task that runs on the first of every month at 1:00am:
	
	  AT 1:00am /every:1 cscript.exe c:\inetpub\adminscripts\mbackup.vbs
	
	Further Help:
	
	Microsoft provides programming examples for illustration only, without warranty
	either expressed or implied, including, but not limited to, the implied
	warranties of merchantability and/or fitness for a particular purpose. This
	article assumes that you are familiar with the programming language being
	demonstrated and the tools used to create and debug procedures. Microsoft
	support professionals can help explain the functionality of a particular
	procedure, but they will not modify these examples to provide added
	functionality or construct procedures to meet your specific needs. If you have
	limited programming experience, you may want to contact a Microsoft Certified
	Partner or the Microsoft fee-based consulting line at (800) 936-5200. For more
	information about Microsoft Certified Partners, please visit the following
	Microsoft Web site:
	
	  http://www.microsoft.com/partner/referral/
	
	For more information about the support options that are available and about how
	to contact Microsoft, visit the following Microsoft Web site:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	REFERENCES
	==========
	
	For additional information on backing up the IIS 5 Metabase, click the article
	number below to view the article in the Microsoft Knowledge Base:
	
	  Q300672 HOW TO: Create a Metabase Backup By Using IIS 5
	
	For more information on Microsoft scripting technologies, see the following
	Microsoft Web site:
	
	  http://msdn.microsoft.com/scripting/
	
	Additional query words: iis 5
	
	======================================================================
	Keywords          :  
	Technology        : kbiisSearch kbiis500
	Version           : :5.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
