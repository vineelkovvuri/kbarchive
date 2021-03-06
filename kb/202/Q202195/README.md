---
layout: page
title: "Q202195: SNMP OID for Logical Disk instance Name Returns Wrong Value"
permalink: /kb/202/Q202195/
---

## Q202195: SNMP OID for Logical Disk instance Name Returns Wrong Value

{% raw %}

	Article: Q202195
	Product(s): Microsoft Windows NT
	Version(s): 4.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 10-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	The object ID, or OID, for the logical disk instance name does not return the
	correct value when issuing an SNMP get or walk command.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Windows NT Server version 4.0.
	
	MORE INFORMATION
	================
	
	Performance Monitor objects can be created by using the PERFMIB utilities from
	the Windows NT 4.0 resource kit. Perform the following steps to create a
	Management Information Base (MIB), which exposes the performance monitor logical
	disk objects:
	
	1. From an MS-DOS command prompt, run the Perfmib.reg utility from the Windows
	  NT 4.0 resource kit. This creates the appropriate registry entries for the
	  Perfmib.dll extension agent.
	
	2. Build a Perfmib.mib and a Perfmib.ini file using the Per2mib.exe utility from
	  the Windows NT 4.0 resource kit. For example, from an MS-DOS command prompt,
	  run the following command:
	
	  "perf2mib perfmib.mib perfmib.ini LogicalDisk 250 disk" (without the
	  quotation marks)
	
	  This creates a Perfmib.mib file and a Perfmib.ini file. These files are used
	  to expose the Performance Monitor logical disk objects.
	
	3. From an MS-DOS command prompt, stop the SNMP service by performing one of the
	  following:
	
	  a. Run the following command:
	
	  "net stop SNMP " (without the quotation marks)
	
	  or
	
	  b. Click Start, point to Settings, click Control Panel, and then double-click
	     Services. Select the SNMP service from the list and then click Stop.
	
	4. Rename the mib file to Mib.old. This file is found in the System32 folder.
	
	5. Compile a new Mib.bin file, which includes the Perfmib.mib file created
	  earlier in step 2. To do this:
	  a. From an MS-DOS command prompt, set the default directory to the Windows NT
	     resource kit folder. For example: "CD %ntreskit%" (without the quotation
	     marks)
	
	  b. Run the following command:
	
	  " mibcc -n o%ntreskit%\mib.bin -t -w2 smi.mib lmmib2.mib mib_ii.mib
	  perfmib.mib " (without the quotation marks)
	
	6. Copy the following files from the Windows NT resource kit folder (%ntreskit%)
	  to the System32 folder (%SystemRoot%\System32):
	   - Mib.bin
	
	   - Perfmib.bin
	
	   - Perfmib.ini
	
	   - Perfmib.dll
	
	7. From an MS-DOS command prompt, start the SNMP service. To do this, perform
	  one of the following:
	  a. Run the following command from an MS-DOS command prompt:
	
	  "net start SNMP" (without the quotation marks)
	
	  or
	
	  b. Click the Start button, point to Settings, click Control Panel, and then
	     double-click Services. Select SNMP from the list, and then click Start.
	
	After the new MIB is created that contains the Performance Monitor logical disk
	objects, it can be tested by using the Snmputil.exe utility found in the
	Microsoft Windows NT resource kit. To test the MIB:
	
	1. From an MS-DOS command prompt, run the command "CD %ntreskit%" (without the
	  quotation marks), to change your default to the resource kit folder.
	
	2. Use the SNMPUTIL utility to walk the logical disk OID tree. To do this, run
	  the following command at an MS-DOS command prompt:
	
	  " snmputil walk localhost public .1.3.6.1.4.1311.1.1.3.1.1.250.1.1 " (without
	  the quotation marks)
	
	  Results: This will successfully walk the tree, but it does not display the
	  logical disk instance name - .1.3.6.1.4.1.311.1.1.3.1.1.250.1.2 - this value
	  is skipped.
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400
	Version           : :4.0
	Issue type        : kbbug
	Solution Type     : kbnofix
	
	=============================================================================
	

{% endraw %}
