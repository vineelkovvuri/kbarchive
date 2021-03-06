---
layout: page
title: "Q183085: PRB: Parameterized RDO Query Results in Error 40002"
permalink: /kb/183/Q183085/
---

## Q183085: PRB: Parameterized RDO Query Results in Error 40002

{% raw %}

	Article: Q183085
	Product(s): Microsoft Visual Basic for Windows
	Version(s): 
	Operating System(s): 
	Keyword(s): kbGrpDSVBDB
	Last Modified: 09-JAN-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Enterprise Edition for Windows, versions 4.0, 5.0, 6.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Some parameterized RDO queries result in Error 40002, "Invalid Parameter
	Number," if the SET NOCOUNT ON/OFF option is used within the SQL query text.
	
	RESOLUTION
	==========
	
	This problem can be resolved by not using a parameter query and instead hard
	coding the parameters in the query string.
	
	To do this, in the code below, comment out the lines of code beneath the PROBLEM
	section. Then uncomment the line of code beneath the WORKAROUND section.
	
	STATUS
	======
	
	Microsoft is researching this problem and will post new information here in the
	Microsoft Knowledge Base as it becomes available.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Behavior
	---------------------------
	
	1. Create a new Visual Basic Standard EXE project and add a reference to the
	  Microsoft Remote Data Object 2.0.
	
	2. Run the following SQL Script against the pubs database to create a table with
	  an Identity field.
	
	        DROP TABLE IdentTest
	        go
	        CREATE TABLE IdentTest
	        (
	        id    INT       IDENTITY,
	        Name   CHAR(20)    NULL
	        )
	        go
	
	3. Add a command button to the default form and add the following code behind
	  the command button's click event. You need to change the connect string to
	  connect to your copy of the pubs database.
	
	        Private Sub Command1_Click()
	
	           Dim MyConnect As rdoConnection
	           Dim Rs As rdoResultset
	           Dim qy As rdoQuery
	           Dim szConnect As String
	
	           szConnect = "Driver={SQL Server}" & _
	             ";Server=YOURSERVERNAME;uid=sa;pwd=;dsn='';Database=pubs"
	
	           Set MyConnect = rdoEnvironments(0).OpenConnection _
	                 (dsname:="", prompt:=rdDriverNoPrompt, Connect:=szConnect)
	
	           Set qy = New rdoQuery
	           Set qy.ActiveConnection = MyConnect
	
	           'PROBLEM SECTION -- Having the (?) parameter in the below line
	           'results in Error 40002
	           '---------------------------------------------------------
	           qy.SQL = "SET NOCOUNT ON INSERT identtest(name)" _
	            & " VALUES( ? ) SELECT @@IDENTITY SET NOCOUNT OFF"
	           qy(0).Direction = rdParamInput  '<<Error 40002 occurs on this line
	           qy(0) = "NewName"
	
	           'WORKAROUND SECTION
	           '----------------------------------------------------------
	           'qy.SQL = "SET NOCOUNT ON INSERT identtest(name)" _
	            & " VALUES('NewName') SELECT @@IDENTITY SET NOCOUNT OFF"
	
	           Set Rs = qy.OpenResultset
	           Debug.Print "The Identity is " & Rs(0).Value
	
	           Set qy = Nothing
	           Set Rs = Nothing
	           Set MyConnect = Nothing
	
	        End Sub
	
	4. Run this code and watch for the Error 40002 to occur on the first line on
	  which qy(0) is referenced.
	
	Additional query words: @@identity kbRDO kbVBp400 kbVBp500 kbVBp600 kbdse kbDSupport kbVBp
	
	======================================================================
	Keywords          : kbGrpDSVBDB 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVB600Search kbVB500 kbVB600 kbVB400Search kbVB400
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
