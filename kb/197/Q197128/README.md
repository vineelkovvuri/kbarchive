---
layout: page
title: "Q197128: BUG: CausesValidation Property Does Not Trigger Validate Event"
permalink: /kb/197/Q197128/
---

## Q197128: BUG: CausesValidation Property Does Not Trigger Validate Event

{% raw %}

	Article: Q197128
	Product(s): Microsoft Visual Basic for Windows
	Version(s): WINDOWS:6.0
	Operating System(s): 
	Keyword(s): kbActivexEvents kbCtrl kbVBp600bug kbGrpDSVB
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Learning Edition for Windows, version 6.0 
	- Microsoft Visual Basic Professional Edition for Windows, version 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 6.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	The Validate event of a control is not executed when it loses focus to another
	control that has its CausesValidation property set to True.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a bug in the Microsoft products listed at the
	beginning of this article.
	
	MORE INFORMATION
	================
	
	Microsoft Visual Basic 6.0 introduced a new Boolean property called
	CausesValidation on various controls, such as the TextBox. According to Visual
	Basic Help, when there is an attempt to put focus on a control that has its
	CausesValidation property set to True, the Validate event of the control that is
	losing focus executes. During that Validate event, you can verify that the data
	entered is valid and you can prevent the shift of focus to the new control if
	you want.
	
	Steps to Reproduce Behavior
	---------------------------
	
	1. Create a new Standard EXE project. Form1 is created by default.
	
	2. Add three TextBox controls to Form1.
	
	3. Set the CausesValidation property in Text1 and Text3 to True.
	
	4. Set the CausesValidation property in Text2 to False.
	
	5. Paste the following code into Form1:
	
	        Private Sub Text1_Validate(Cancel As Boolean)
	           Debug.Print "Text1's Validate Event"
	        End Sub
	
	        Private Sub Text2_Validate(Cancel As Boolean)
	           Debug.Print "Text2's Validate Event"
	        End Sub
	
	        Private Sub Text3_Validate(Cancel As Boolean)
	           Debug.Print "Text3's Validate Event"
	        End Sub
	
	6. Run the sample project.
	
	7. The focus begins on Text1. Click Text3. The CausesValidation property of
	  Text3, set to True, causes the Validate event of Text1 to be executed as
	  expected.
	
	8. With the focus on Text3, click Text2. The CausesValidation property of Text2,
	  set to False, does not cause the Validate event of Text3 as expected.
	
	9. With the focus on Text2, click Text3. The CausesValidation property of Text3,
	  set to True, does not cause the Validate event of Text2 as it should.
	
	With the CausesValidation property of Text2 set to False, there does not appear
	to be any way to get a Validate event for Text2 to execute.
	
	Aside from attempting to use the LostFocus event to manually call a Validate
	event for Text2 from Text2, you can work around this problem by changing the
	CausesValidation property from False to True.
	
	Additional query words: kbdsd Causes Validation
	
	======================================================================
	Keywords          : kbActivexEvents kbCtrl kbVBp600bug kbGrpDSVB 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB600Search kbVBA600 kbVB600
	Version           : WINDOWS:6.0
	Issue type        : kbbug
	Solution Type     : kbpending
	
	=============================================================================
	

{% endraw %}
