---
layout: page
title: "Q137952: How to Set Up Relationship in Data Env for Concatenated Fields"
permalink: /kb/137/Q137952/
---

## Q137952: How to Set Up Relationship in Data Env for Concatenated Fields

{% raw %}

	Article: Q137952
	Product(s): Microsoft FoxPro
	Version(s): WINDOWS:3.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 11-DEC-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, version 3.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Use the following steps to create a relationship involving the concatenation of
	two or more fields in the parent and child tables in the data environment of a
	form or report:
	
	1. Create an index tag in the child table from the concatenation of the fields.
	
	2. Add the parent and child tables to the data environment.
	
	3. In the data environment, drag the first field of the concatenation from the
	  parent table to the concatenated index tag in the child.
	
	4. Bring up the Property sheet for the Relation object and set its
	  RelationalExpr property to the concatenation of the fields (field1+field2 if
	  the fields are both character data type).
	
	MORE INFORMATION
	================
	
	Step-by-Step Example
	--------------------
	
	This example uses a program that creates the parent and child tables.
	
	1. Run the following program to create the tables to be used:
	
	     * Start of CREATABS.PRG
	
	     * This program creates a parent table called PAR_TAB.DBF and a child
	     * table called CHLD_TAB.DBF
	
	     * Create and fill parent table
	
	     CREATE TABLE par_tab FREE (cfield1 C (3), cfield2 C(3))
	
	     FOR nI=1 TO 10
	        FOR nJ=1 TO 3
	          INSERT INTO par_tab (cfield1,cfield2) ;
	            VALUES (CHR(64+nI), ALLTRIM(STR(nJ)))
	        ENDFOR
	     ENDFOR
	
	     * Create and fill child table
	     CREATE TABLE chld_tab FREE (cfield1 C (3), cfield2 C(3), cfield3 C(3))
	
	     FOR nI=1 TO 10
	        FOR nJ=1 TO 3
	           FOR nK=1 TO nJ
	             INSERT INTO chld_tab (cfield1,cfield2,cfield3) ;
	               VALUES (CHR(64+nI),ALLTRIM(STR(nJ)),ALLTRIM(STR(nK)))
	           ENDFOR
	        ENDFOR
	     ENDFOR
	
	     * End of CREATABS.PRG
	
	2. Modify the structure of Chld_tab.dbf and create the concatenated index tag.
	  Name the index tag Cfld1cfld2, and in the index expression, enter
	  Cfield1+Cfield2.
	
	3. Create a form, and add Par_tab.dbf and Chld_tab.dbf to the data environment
	  of the form.
	
	4. Drag the first field in the concatenation (Cfield1) from Par_tab.dbf and drop
	  it on the Cfld1cfld2 index tag of Chld_tab.dbf. This creates a relationship.
	
	5. Right-click the relationship line in the data environment, and click
	  Properties to bring up the Property sheet. Edit the RelationalExpr property
	  of the Relation1 object. This will now contain Cfield1. Edit this to read
	  Cfield1+Cfield2 -- the same thing entered as the index expression for the
	  Chld_tab table. The relationship is now established.
	
	6. Drag Cfield1 and Cfield2 from the parent table and onto the form to create
	  text boxes. Drag the child table by its title bar onto the form to create a
	  grid.
	
	7. Add a command button to the form with the following code in its Click event:
	
	     SKIP
	     Thisform.Refresh
	
	8. Save and run the form. Click the command button to move the record pointer
	  through the parent table. Note that the values in the text boxes from the
	  parent table match the first two columns of the grid, which are the
	  corresponding fields in the child table.
	
	Additional Notes
	----------------
	
	- The first table added to the data environment is initially selected by
	  default. If the child table is added to the data environment first, the
	  InitialSelectedAlias property of the DataEnvironment object should be set to
	  the parent table name.
	
	- After the relationship is established as previously described, the line
	  representing the relationship in the data environment comes from the Fields
	  heading in the parent.
	
	- The structure of each of the fields in the concatenation must be identical in
	  the parent and the child.
	
	- Although the previous example uses a form, the data environment setup is the
	  same for a report.
	
	- If numeric fields must be concatenated, they must be first converted to
	  strings. For example, str(nfield1)+str(nfield2) could be used for two numeric
	  fields in the index expression of the child table and the RelationalExpr of
	  the Relation object. Likewise, a character and numeric field could be
	  concatenated with the expression cfield1+str(nfield2).
	
	Additional query words: VFoxWin
	
	======================================================================
	Keywords          :  
	Technology        : kbVFPsearch kbAudDeveloper kbVFP300
	Version           : WINDOWS:3.0
	
	=============================================================================
	

{% endraw %}
