---
layout: page
title: "Q129500: PC Adm: Automating the Resetting of Group Files with GIMPORT"
permalink: /kb/129/Q129500/
---

## Q129500: PC Adm: Automating the Resetting of Group Files with GIMPORT

{% raw %}

	Article: Q129500
	Product(s): Microsoft Mail For PC Networks
	Version(s): WINDOWS:2.1,3.0,3.2
	Operating System(s): 
	Keyword(s): 
	Last Modified: 30-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Mail for PC Networks, versions 2.1, 3.0, 3.2 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article describes how the Microsoft Mail Group Import Program, GIMPORT.EXE
	version 3.5 and later, can be used to automate the process of removing all
	Microsoft Mail Postoffice Address List Groups and resetting the group files.
	
	MORE INFORMATION
	================
	
	GIMPORT.EXE version 3.5 and later has a command line option, -r, which when used
	will remove all Postoffice Address List Groups and reset all relevant group
	files to their default states. Before you run GIMPORT.EXE, it is advisable to
	read the Application Note that accompanies the GIMPORT.EXE. Also, it is
	recommended that you backup the following directories of your Microsoft Mail
	postoffice: GLB, GRP, NME, and MEM.
	
	The following command shows how to run GIMPORT.EXE to remove all the Postoffice
	Address List Groups and reset the group files:
	
	  GIMPORT -dm admin -p<password> -r -v -lgimport.log
	
	where,
	
	- the Microsoft Mail postoffice is located on drive M.
	
	- admin is a Microsoft Mail account with Administrative privilege.
	
	- <password> refers to the password for the 'admin' account.
	
	When the above command is run, GIMPORT.EXE will reset the following files:
	
	- ADMIN.GRP and ADMINSHD.GRP to 8 bytes, which are set to zeroes.
	
	- GROUP.GLB to 4 bytes, which are set to zeroes.
	
	- GRPMEM.GLB to 4 bytes, which are set to zeroes.
	
	In addition, the groups are removed from the ADMIN.NME and ADMINSHD.NME. All
	non-deleted records in the ACCESS.GLB file are modified to reset the pointer
	into the GRPMEM.GLB. All the .MEM files are removed from the MEM directory.
	
	For more information about the GIMPORT.EXE utility, please see the following
	article in the Microsoft Knowledge Base:
	
	  Q99419 PC DB: Database Maintenance Utilities (Complete)
	
	Additional query words: 2.10 3.00 3.20 appnote
	
	======================================================================
	Keywords          :  
	Technology        : kbMailSearch kbZNotKeyword3 kbMailPCN320 kbMailPCN300 kbMailPCN210
	Version           : WINDOWS:2.1,3.0,3.2
	
	=============================================================================
	

{% endraw %}
