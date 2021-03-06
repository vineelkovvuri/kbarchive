---
layout: page
title: "Q131934: ACC: Cannot Reference OLE Control in Datasheet View"
permalink: /kb/131/Q131934/
---

## Q131934: ACC: Cannot Reference OLE Control in Datasheet View

{% raw %}

	Article: Q131934
	Product(s): Microsoft Access Distribution Kit
	Version(s): WINDOWS:2.0,7.0,97
	Operating System(s): 
	Keyword(s): kberrmsg kbusage
	Last Modified: 05-JUL-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Access 2.0 
	- Microsoft Access for Windows 95, version 7.0 
	- Microsoft Access 97 
	-------------------------------------------------------------------------------
	
	Moderate: Requires basic macro, coding, and interoperability skills.
	
	
	SYMPTOMS
	========
	
	When you reference a form's OLE control in an expression or a procedure, you may
	receive the following error message.
	
	In Microsoft Access 97
	----------------------
	
	  Run-time error '2771': The bound or unbound object frame you tried to edit
	  doesn't contain an OLE object.
	
	  Use the Object command on the Insert menu to add an OLE object to the bound or
	  unbound object frame.
	
	In Microsoft Access for Windows 95 version 7.0
	----------------------------------------------
	
	  The unbound or bound object frame you tried to edit doesn't contain an OLE
	  object.
	
	In Microsoft Access version 2.0
	-------------------------------
	
	  Can't obtain this property setting. The property may not be available in this
	  view, or an error may have occurred.
	
	CAUSE
	=====
	
	When a form is open in Datasheet view, you cannot reference the form's unbound
	OLE control.
	
	RESOLUTION
	==========
	
	Do not reference OLE controls in forms that are displayed in Datasheet view.
	
	NOTE: You can check a form's CurrentView property setting to determine whether
	the form is displayed in Datasheet, Form, or Design view.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft Access 2.0, 7.0, and
	97. We are researching this problem and will post new information here in the
	Microsoft Knowledge Base as it becomes available.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Problem
	--------------------------
	
	1. Create a new form not based on a table or query.
	
	2. Insert the Calendar Control.
	
	3. In the Properties dialog box, change the name of the Calendar Control to
	  "CalendarCtl" (without the quotation marks).
	
	4. View the form in Datasheet view
	
	5. Open the Debug window (or Immediate window in version 2.0), and type the
	  following line:
	
	  ? Forms!Form1!CalendarCtl.object.value
	
	  Note that you receive an error message because the form that the expression
	  references is open in Datasheet view.
	
	REFERENCES
	==========
	
	For more information about the CurrentView property, search the Help Index for
	"CurrentView Property," or ask the Microsoft Access 97 Office Assistant.
	
	Additional query words: ocx custom control activex run time error 2771
	
	======================================================================
	Keywords          : kberrmsg kbusage 
	Technology        : kbAccessSearch kbAccess200 kbAccess97 kbAccess97Search kbAccess95Search kbZNotKeyword3 kbAccess700
	Version           : WINDOWS:2.0,7.0,97
	Hardware          : x86
	Issue type        : kbbug
	
	=============================================================================
	

{% endraw %}
