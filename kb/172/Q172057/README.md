---
layout: page
title: "Q172057: FIX: CreateDragImage Method in ListView Uses Wrong Icon"
permalink: /kb/172/Q172057/
---

## Q172057: FIX: CreateDragImage Method in ListView Uses Wrong Icon

{% raw %}

	Article: Q172057
	Product(s): Microsoft Visual Basic for Windows
	Version(s): 
	Operating System(s): 
	Keyword(s): kbGrpDSVB
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Professional Edition for Windows, version 5.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 5.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When dragging a selection from the ListView control, the icon for the first item
	in the list is displayed during the drag operation. This problem occurs when the
	CreateDragImage method is used.
	
	RESOLUTION
	==========
	
	To work around this problem, it is necessary to extract the correct icon from
	the image list that provides the icons for the ListView. For example, if the
	original line of code reads:
	
	     ListView1.DragIcon = ListView1.SelectedItem.CreateDragImage
	
	change it to read:
	
	     ListView1.DragIcon= _
	     ImageList1.ListImages(ListView1.SelectedItem.Index).ExtractIcon
	
	STATUS
	======
	
	Microsoft has confirmed this to be a bug in the Microsoft products listed at the
	beginning of this article. This bug has been fixed in Visual Basic 6.0.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Behavior
	---------------------------
	
	1. Create a new "Standard EXE" project.
	
	2. On the default form, place an ImageList, a ListView, and a label.
	
	3. Set the View property of the ListView control to "2-lvwList."
	
	4. Place the following code in the Forms module:
	
	     Dim itmX As ListItem
	
	     Private Sub Form_Load()
	     Dim i As Integer
	     ListView1.Icons = ImageList1
	     ListView1.SmallIcons = ImageList1
	     For i = 1 To 4
	        Set itmX = ListView1.ListItems.Add(i, , "List item " + Str(i), i, i)
	     Next
	     End Sub
	
	     Private Sub ListView1_MouseDown(Button As Integer, Shift As Integer, _
	        x As Single, y As Single)
	     Set itmX = ListView1.SelectedItem ' Set the item being dragged.
	     End Sub
	
	     Private Sub listView1_MouseMove(Button As Integer, Shift As Integer, _
	        x As Single, y As Single)
	     If Button = vbLeftButton Then ' Signal a Drag operation.
	        Label1.Caption = ListView1.SelectedItem 'Check which item is selected
	        ListView1.DragIcon = ListView1.SelectedItem.CreateDragImage
	        'workaround
	        'ListView1.DragIcon = _
	        '  ImageList1.ListImages(ListView1.SelectedItem.Index).ExtractIcon
	        ListView1.Drag vbBeginDrag ' Drag operation.
	    End If
	    End Sub
	
	5. Run the project.
	
	6. Drag a selection from the ListView. Note that the icon used for the drag
	  operation is always the first icon in the ListView control.
	
	Additional query words: kbVBp500bug kbVBp600fix kbVBp kbdsd kbDSupport kbControl kbCreate
	
	======================================================================
	Keywords          : kbGrpDSVB 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVBA500 kbVB500
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
