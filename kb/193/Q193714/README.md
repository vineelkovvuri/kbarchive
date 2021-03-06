---
layout: page
title: "Q193714: WD97: Queries Not Available When Using Access Database"
permalink: /kb/193/Q193714/
---

## Q193714: WD97: Queries Not Available When Using Access Database

{% raw %}

	Article: Q193714
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbdta word97 kbmerge
	Last Modified: 14-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	When you use a Microsoft Access database file as a data source in Word,
	Microsoft Access queries may not be available. Instead, the Select Table dialog
	box is available for you to select which Microsoft Access table you want to
	use.
	
	For additional information on how to use a Microsoft Access database file in
	Word, please see the following article in the Microsoft Knowledge Base:
	
	  Q193716 WD97: How to Use Microsoft Access 97 Data in Word
	
	CAUSE
	=====
	
	Microsoft Word 97 for Windows may be using the "MS Access 97 Database via ODBC
	(*.mdb)" driver to open your Microsoft Access database file. When Word uses this
	driver, Microsoft Access queries are not available by default.
	
	RESOLUTION
	==========
	
	Use one of the following methods to access your Microsoft Access database
	queries:
	
	Method 1: Change the Select Table Options
	-----------------------------------------
	
	1. In the Select Table dialog box, click Options.
	
	2. Under Show, click to clear the Tables check box and then select the Views
	  check box.
	
	3. Click OK to close the Table Options dialog box.
	
	Your Microsoft Access queries should now be available in the Table list of the
	Select Table dialog box.
	
	Method 2: Use DDE to Connect to Your Microsoft Access Database
	--------------------------------------------------------------
	
	1. In the Select Table dialog box, click Cancel.
	
	2. If you are using a Microsoft Access database as a data source in a Word mail
	  merge, in the Mail Merge Helper (on the Tools menu, click Mail Merge), click
	  Get Data and then click Open Data Source.
	
	  -or-
	
	  If you are inserting a Database in a Word document, in the Database dialog box
	  (on the Database toolbar, click Insert Database), click Get Data.
	
	  NOTE: To access the Database toolbar, on the View menu, point to Toolbars and
	  then click Database.
	
	3. In the Open Data Source dialog box, follow these steps:
	
	  a. Change the Files of type box to "MS Access Databases (*.mdb)."
	
	  b. Select your Microsoft Access database file.
	
	  c. Click to select the Select Method check box.
	
	  d. Click Open.
	
	4. In the Confirm Data Source dialog box, select "MS Access Databases via DDE
	  (*.mdb)" and then click OK.
	
	  NOTE: If "MS Access Databases via DDE (*.mdb)" is not available, you will need
	  to remove and then reinstall Microsoft Access 97 for Windows.
	
	5. In the Microsoft Access dialog box, click the Queries tab.
	
	Your Microsoft Access queries should now be available.
	
	Additional query words: datasource msaccess
	
	======================================================================
	Keywords          : kbdta word97 kbmerge 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
