---
layout: page
title: "Q129388: INFO: How Null String Pointers Behave in Visual Basic 4.0"
permalink: /kb/129/Q129388/
---

## Q129388: INFO: How Null String Pointers Behave in Visual Basic 4.0

{% raw %}

	Article: Q129388
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:4.0
	Operating System(s): 
	Keyword(s): kbprogramming kbVBp400
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Standard Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 32-bit, for Windows, version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Visual Basic version 4.0 recognizes two very different kinds of strings that
	look the same but act differently. One is a Null pointer string, the other is an
	empty string. You might code them in a public module as follows:
	
	     Public sNull As String
	     Public Const sEmpty = ""
	
	If you look at these two strings in the Watch window, they look exactly the same;
	both displayed as "". You can use them in almost the same contexts, but
	internally they are very different.
	
	MORE INFORMATION
	================
	
	Internally, sNull is a null pointer. It does not point to any memory location
	and has a value of zero. In C, you would code it as:
	
	     const char *sNull = NULL;
	
	Internally, sEmpty is a pointer to an empty string. It is a valid pointer to some
	memory location. In C, you would code it as:
	
	     const char sEmpty[] = "";
	
	All Visual Basic version 4.0 variables are set to zero (0) until initialized. In
	previous versions of Visual Basic, uninitialized variable-length strings were
	automatically set to an empty string (""). Therefore, for compatibility with
	previous versions, you might think that you must initialize string variables to
	empty strings. However, Visual Basic version 4.0 strings are in the BSTR format
	where a null pointer is defined to behave exactly as an empty string does.
	Therefore, in Visual Basic version 4.0, you can leave the initial zero value of
	an uninitialized strings alone because it will behave as if it were an empty
	string.
	
	This means that sNull can now be passed to any Windows API function that takes a
	Null pointer. This is something that was not possible in previous versions of
	Visual Basic. For example, it can be passed to FindWindow, which gets the handle
	of a window, given either its class name or its title, or both. However for this
	to work, sNull must be passed ByVal.
	
	In general, for FindWindow (or any other Windows API) to work, the Declare
	statement must be written to pass the string ByVal As String or ByVal As Any. If
	the string is passed by reference, a pointer to a BSTR would then be passed,
	which is nothing but a pointer to a pointer to char. This will not work as
	Windows APIs expect strings that are pointers to char.
	
	NOTE: In Visual Basic version 4.0, sNull might also be expected to be equivalent
	to:
	
	     Public Const sNull As String = 0&
	
	However, Visual Basic does automatic numeric conversion on this and converts it
	to zero (0), which is neither an empty string nor a null string pointer.
	
	Step-by-Step Example
	--------------------
	
	1. Start a new project in Visual Basic. Form1 is created by default.
	
	2. Add the following code to the General Declarations section of Form1:
	
	              Const sEmpty = ""
	        Dim sNull As String
	
	        Private Declare Function FindWindow Lib "user32" Alias _
	           "FindWindowA" (ByVal lpClassName As Any, ByVal _
	           lpWindowName As Any) As Long
	
	3. In the Form_Click event for Form1, add the following code:
	
	        Shell "Calc.exe", 1
	        DoEvents
	        x& = FindWindow(sNull, "Calculator")
	        'x& = FindWindow(sEmpty, "Calculator")
	        Debug.Print x&
	
	4. Press the F5 key to run the program. Click Form1, and view the Debug Window.
	  A non-zero value will be printed. This is the handle of the Calculator
	  program's Window.
	
	5. As an experiment, change the following line from executed code into a
	  comment:
	
	        x& = FindWindow(sNull, "Calculator")
	
	  And change the following line from a comment into executed code:
	
	        'x& = FindWindow(sEmpty, "Calculator")
	
	  Then run the program again. You will see a value of zero (0) printed in the
	  Debug Window, indicating that FindWindow failed. This happens because sEmpty
	  is not a null string pointer.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbprogramming kbVBp400 
	Technology        : kbVBSearch kbAudDeveloper kbVB400Search kbVB400 kbVB16bitSearch
	Version           : WINDOWS:4.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
